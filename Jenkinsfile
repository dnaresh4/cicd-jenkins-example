pipeline {

    agent any
    tools { 
        MAVEN_HOME 'Maven 3.5.0' 
        JAVA 'jdk8' 
    }
    stages {
         stage ('Initialize') {
            steps {
                sh '''
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
               
                    sh 'mvn clean package'
            }
        }

        stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {

                    sh '/usr/local/bin/cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD'
                    sh '/usr/local/bin/cf push'
                }
            }

        }

    }

}
