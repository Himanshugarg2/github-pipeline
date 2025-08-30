pipeline {
    agent any

    tools {
        nodejs "NodeJS"  
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Pulling code from GitHub..."
                checkout scm
            }
        }

        stage('Install Dependencies') {
    steps {
        dir('my-app') {    
            sh 'npm install'
        }
    }
}


        stage('Build') {
            steps {
                echo "Building React app..."
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'npm test -- --watchAll=false'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying React app..."
                
            }
        }
    }

    post {
        success {
            echo "React pipeline executed successfully "
        }
        failure {
            echo "React pipeline failed"
        }
    }
}
