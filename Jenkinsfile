pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials') // Make sure to set up Docker Hub credentials in Jenkins
        DOCKERHUB_REPO = 'nabeel'
        ROLL_NUMBER = '20i-0999'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo '20i-0999 - Checking out code from GitHub'
                    checkout scm
                }
            }
        }

        stage('Build and Push Event-Bus Image') {
            steps {
                script {
                    echo '20i-0999 - Building Docker image for Event-Bus'
                    dir('event-bus') {
                        sh 'docker build -t ${DOCKERHUB_REPO}/event-bus:${ROLL_NUMBER} .'
                        sh 'docker push ${DOCKERHUB_REPO}/event-bus:${ROLL_NUMBER}'
                    }
                }
            }
        }

        stage('Build and Push Auth Image') {
            steps {
                script {
                    echo '20i-0999 - Building Docker image for Auth'
                    dir('Auth') {
                        sh 'docker build -t ${DOCKERHUB_REPO}/auth:${ROLL_NUMBER} .'
                        sh 'docker push ${DOCKERHUB_REPO}/auth:${ROLL_NUMBER}'
                    }
                }
            }
        }

        stage('Build and Push Classrooms Image') {
            steps {
                script {
                    echo '20i-0999 - Building Docker image for Classrooms'
                    dir('Classrooms') {
                        sh 'docker build -t ${DOCKERHUB_REPO}/classrooms:${ROLL_NUMBER} .'
                        sh 'docker push ${DOCKERHUB_REPO}/classrooms:${ROLL_NUMBER}'
                    }
                }
            }
        }

        stage('Build and Push Post Image') {
            steps {
                script {
                    echo '20i-0999 - Building Docker image for Post'
                    dir('Post') {
                        sh 'docker build -t ${DOCKERHUB_REPO}/post:${ROLL_NUMBER} .'
                        sh 'docker push ${DOCKERHUB_REPO}/post:${ROLL_NUMBER}'
                    }
                }
            }
        }

        stage('Build and Push Frontend Image') {
            steps {
                script {
                    echo '20i-0999 - Building Docker image for Frontend'
                    dir('client') {
                        sh 'docker build -t ${DOCKERHUB_REPO}/frontend:${ROLL_NUMBER} .'
                        sh 'docker push ${DOCKERHUB_REPO}/frontend:${ROLL_NUMBER}'
                    }
                }
            }
        }
    }
}
