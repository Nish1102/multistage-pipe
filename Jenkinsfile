pipeline {
    agent {
        docker {
            image 'nish1102/gitprofile:latest'
        }
    }
    stages {
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
                // Add your actual deployment commands here

                // Run the Docker container and expose it on port 45
                sh 'docker run -p 45:80 -d nish1102/gitprofile:latest'
            }
        }
    }
}
