pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build stage
                    docker.build('nish1102/gitprofile', '-f Dockerfile.build .')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Test stage
                    docker.build('nish1102/gitprofile:latest', '-f Dockerfile.test .')
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy stage
                    docker.build('nish1102/gitprofile:latest', '-f Dockerfile.deploy .')
                }
            }
        }

        stage('Run Locally') {
            steps {
                script {
                    // Run the container locally on port 45
                    def containerId = docker.image('nish1102/gitprofile:latest').run("-p 45:80 --name my-container -d")
                    // Save the container ID for later cleanup
                    env.CONTAINER_ID = containerId
                }
            }
        }
    }

    post {
        always {
            // Cleanup stage
            script {
                // Stop and remove the container
                sh "docker stop ${env.CONTAINER_ID}"
                sh "docker rm ${env.CONTAINER_ID}"

                // Additional debugging information
                sh 'docker version'
                sh 'docker info'
                sh 'which docker'
                sh 'docker images'
                sh 'docker ps -a'
            }
        }
    }
}
