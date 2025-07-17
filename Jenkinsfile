pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/tyltnine/crispy-succotash.git'
            }
        }

        stage('Build') {
            steps {
                sh './mvnw clean compile'
            }
        }

        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }

        stage('Package') {
            steps {
                sh './mvnw package'
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar target/MySpringBootApp-0.0.1-SNAPSHOT.jar &'
            }
        }
    }
}