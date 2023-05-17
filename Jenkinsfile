pipeline {
    agent {
        docker {
            image 'node:lts-alpine'
            args '-p 3000:3000 -p 5000:5000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        
        
        stage('Deploy for production') {
            
            steps {
                 sh 'sudo chmod +x ./deploy.sh'
                sh './deploy.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                
            }
        }
    }
}
