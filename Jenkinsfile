node {
  
   stage('SCM Checkout'){
	url: 'https://github.com/dnaresh4/cicd-jenkins-example'
   
   }
    stage('Compile-Package'){
	   // Build using maven  
	   sh 'mvn package'
   }
}
