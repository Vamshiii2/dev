pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                 git url: 'https://github.com/Vamshiii2/dev.git', branch: 'main', credentialsId: 'github-pat'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('vamshi0007gangammahello-world-python')
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'github-pat') {
                              docker.image('vamshi0007gangamma/hello-world-python').push('latest')
                    }
                }
            }
        }
    }
}
