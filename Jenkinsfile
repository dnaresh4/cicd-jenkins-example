pipeline {

    agent any
	tools {
    maven 'MAVEN_HOME'
  }
    stages {
        stage ('Build') {
            steps {
            withMaven(maven: 'MAVEN_HOME') {
                bat "mvn clean install"     
                }
            }
        }
	    stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {
                        echo "${USERNAME}"
                    bat 'cf login -a http://api.run.pivotal.io -u $USERNAME -p $PASSWORD'
                    bat 'cf push'
                }
            }

        }
    }
}
