pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "raguldochub/ragul-capstone-app:devops"
        CONTAINER_NAME = "ragul-app"
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Ragulgit-hub/Ragul-Capstone-Github.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ragul-capstone-app:devops .'
            }
        }

        stage('Tag Image') {
            steps {
                sh 'docker tag ragul-capstone-app:devops raguldochub/ragul-capstone-app:devops'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                    sh 'docker push raguldochub/ragul-capstone-app:devops'
                }
            }
        }

        stage('Deploy on EC2') {
            steps {
                sh '''
                docker rm -f ragul-app || true
                docker run -d -p 3000:3000 --name ragul-app raguldochub/ragul-capstone-app:devops
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful 🚀'
        }
        failure {
            echo 'Deployment Failed ❌'
        }
    }
}
