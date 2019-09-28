node {
  
   stage('SCM Checkout'){
	url: 'https://github.com/dnaresh4/cicd-jenkins-example'
   
   }
    stage('Compile-Package'){
	   // Build using maven
	    def mvnhome=tool name: 'MAVEN_HOME', type: 'maven'
	    sh "${mvnhome}/bin/mvn package"
   }
}
