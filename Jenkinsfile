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
                checkout ___
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ___ .'
            }
        }

    }

    post {
        success {
            echo 'Build succeeded. Image: ___ built successfully.'
        }
        failure {
            echo 'Build failed. Check the console output above.'
        }
    }
}
