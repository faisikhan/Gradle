pipeline {
    agent any

    stages {
    stage('Clone Git') {
      steps {
        git([url: 'git@github.com:faisikhan/gradle.git', credentialsId: 'githubcreds', branch: 'master'])

         }
       }
     }  
        stage('Build') {
            steps {
                sh './gradlew assemble'
            }
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('Build Docker image') {
            steps {
                sh './gradlew docker'
            }
        }
        stage('Push Docker image') {
            environment {
                DOCKER_HUB_LOGIN = credentials('hub')
            }
            steps {
                sh './gradlew dockerPush'
            }
        }
    }
}
