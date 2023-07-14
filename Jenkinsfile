pipeline {
    agent any
    environment {
        APP_VERSION = '1.10.3'
        APP_CREDENTIALS = credentials('app_credentials')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo "Building with version ${APP_VERSION}"
                sleep 3
            }
        }
        stage('Test') {
            steps {
                echo 'UT Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                echo "Deploying with credentials ${APP_CREDENTIALS}"
                sleep 3
            }
        }
        stage('Release') {
            steps {
                echo 'Releasing...'
                withCredentials([
                    usernamePassword(credentialsId: 'app_credentials', usernameVariable: 'USER', passwordVariable: 'PWD')
                ]) {
                    echo "User: ${USER}, PWD: ${PWD}"
                }
            }
        }
    }
}