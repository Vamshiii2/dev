pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/hello-world-python.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('hello-world-python')
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'Vinu') {
                        docker.image('hello-world-python').push('latest')
                    }
                }
            }
        }
    }
}
