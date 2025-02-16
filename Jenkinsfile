pipeline {
    agent { label 'linux' }
    environment {
        MY_ENV_VAR = 'value'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/my/repository.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'  // for example, a Maven build
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/myapp.war user@server:/deploy/path/'
            }
        }
    }
    post {
        always {
            echo 'This will always run after the pipeline execution.'
        }
        success {
            echo 'The pipeline was successful!'
        }
        failure {
            echo 'The pipeline failed!'
        }
    }
}
