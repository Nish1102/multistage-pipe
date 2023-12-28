pipeline {
    agent {
        docker {
            image 'nish1102/gitprofile:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                // No build steps needed for a simple HTML, CSS, and JavaScript project
            }
        }

        stage('Test') {
            steps {
                // Run basic tests for the HTML file
                sh 'cd your/project/directory'
                sh 'python -m http.server 45 &'
                sh 'sleep 5' // Wait for the server to start
                sh 'wget http://localhost:45'
            }
        }

        stage('Deploy') {
            steps {
                // No deployment steps needed for a simple project
            }
        }
    }
}
