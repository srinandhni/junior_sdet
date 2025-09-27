pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/srinandhni/junior_sdet.git'
            }
        }

        stage('Build') {
            steps {
                mvn clean install
            }
        }

        stage('Test') {
            steps {
              mvn test
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying application...'
            }
        }
    }
}