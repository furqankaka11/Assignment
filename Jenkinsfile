pipeline {
     def app 
     stage('clone repository') {
     git 'https://github.com/furqankaka11/assignment.git'
    }
     stage('Build docker Image'){
      app = docker.build("furqan1111/assignment")
    }
     stage('Test Image'){
       app.inside {
         sh 'echo "TEST PASSED"'
      }  
    }
     stage('Push Image'){
       docker.withRegistry('https://registry.hub.docker.com', 'git') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")   
   }
}
}
