pipeline {
    agent any

    environment {
        IMAGE_NAME = 'snapcart'
        IMAGE_TAG  = "${env.BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                // Jenkins checks out your repository automatically
                // when Pipeline script from SCM is configured.
                // This stage makes the step explicit.
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t ${env.IMAGE_NAME}:${env.IMAGE_TAG} ."
            }
        }

    }

    post {
        success {
            echo "Build succeeded. Image: ${env.IMAGE_NAME}:${env.IMAGE_TAG} built successfully."
        }
        failure {
            echo 'Build failed. Check the console output above.'
        }
    }
}
//Successfully built snapcart:1
//Update 1