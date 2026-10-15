
pipeline {
    agent any

    stages {
        stage('Get Source Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Project') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn sonar:sonar'
                }
            }
        }
    }
}
