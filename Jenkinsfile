pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'docker rmi karimshan/docker-repo:latest -f'
                sh 'docker build -t karimshan/docker-repo:latest . '
            }
        }
        
        stage('login') {
            steps {
                sh 'docker login -u karimshan -p Karimshan121'
           }
        }
        
        stage('push') {
            steps {
        sh 'docker push karimshan/docker-repo:latest'
      
            }
        }   
        
        
        
       }    
}
