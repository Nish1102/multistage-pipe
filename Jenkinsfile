pipeline {
    agent any

    stages {
        stage('Check Docker') {
            steps {
                script {
                    // Check Docker installation
                    sh 'docker --version'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your actual build commands here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your actual test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                
                // Run the Docker container and expose it on port 45
                sh 'docker run -p 45:80 -d nish1102/gitprofile:latest'
            }
        }
    }
}



