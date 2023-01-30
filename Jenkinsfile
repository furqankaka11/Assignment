pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'docker rmi furqan1111/furqan:latest -f'
                sh 'docker build -t furqan1111/furqan:latest . '
            }
        }
        
        stage('login') {
            steps {
                sh 'docker login -u furqan1111-p Furqan1111'
           }
        }
        
        stage('push') {
            steps {
        sh 'docker push furqan1111/furqan:latest'
      
            }
        }   
        
       }    
}
