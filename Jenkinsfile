node {
    try {
        stage('Checkout') {
            echo "Pulling code from GitHub..."
            checkout scm
        }

        stage('Install Dependencies') {
            dir('my-app') {
                sh 'npm install'
            }
        }

        stage('Build') {
            dir('my-app') {
                echo "Building React app..."
                sh 'npm run build'
            }
        }

        stage('Test') {
            dir('my-app') {
                echo "Running tests..."
                sh 'npm test -- --watchAll=false --passWithNoTests'
            }
        }

        stage('Deploy') {
            dir('my-app') {
                echo "Deploying React app..."
                // put deploy steps here
            }
        }

        echo "React pipeline executed successfully!"
    } catch (err) {
        echo "React pipeline failed!"
        throw err
    }
}
