pipeline {

    agent any
	tools {
    maven 'MAVEN_HOME'
  }
    stages {
        stage ('Build') {
            steps {
            withMaven(maven: 'MAVEN_HOME') {
                    sh 'mvn clean package'
                }
            }
        }
    }
}
