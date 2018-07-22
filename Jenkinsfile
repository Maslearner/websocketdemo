node {

   stage('Clone Repository') {
        // Get some code from a GitHub repository
        git 'https://github.com/Maslearner/websocketdemo.git'

   }
   stage('RHC Client Test'){
	//Testing rhc tool installation ans setup
	//sh "rhc"
	//sh "rhc --version"
   }

   stage('compile') {
      
        sh 'mvn clean install'
      
   }
   
  
   stage('Deploy Spring Boot Application') {

       //Remove maven-build-container if it exisits
       //sh " docker rm -f akeeb-deploy-websocket"

       //sh " docker run --name akeeb-deploy-websocket --volumes-from akeeb-build-websocket -d -p 8093:8083 akeeb/websocket"
	
	sh "docker run -p 5002:8080 --name akeeb-deploy-websocket mashuk/spring-boot-websocket-chat-demo:0.0.1-SNAPSHOT"
   }

}
