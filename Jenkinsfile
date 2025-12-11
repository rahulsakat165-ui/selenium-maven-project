pipeline {
    agent any
    tools {
        maven 'Maven-3.9.11'

    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/rahulsakat165-ui/selenium-maven-project.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                bat 'mvn test'
            }
        }
    }
    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
