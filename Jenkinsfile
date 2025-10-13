pipeline {
    agent any
    tools{
        maven 'Maven-3.9.9'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/srinandhni/junior_sdet.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
              bat 'mvn test'
            }
        }

        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
