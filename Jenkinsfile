node {
  
   stage('SCM Checkout'){
	url: 'https://github.com/javahometech/myweb'
   
   }
    stage('Compile-Package'){
	   // Build using maven  
	   sh 'mvn package'
   }
}
