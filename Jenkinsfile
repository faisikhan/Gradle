pipeline {
  environment {
    imagename = "frehman/pipe1"
    registryCredential = 'hub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Clone Git') {
      steps {
        git([url: 'git@github.com:faisikhan/gradle.git', credentialsId: 'githubcreds', branch: 'master'])

      }
    }
        stage('Build') {
            steps {
                sh './gradlew assemble'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('Build Docker image') {
            steps {
                dockerImage = docker.build imagename
                }
        }
          stage('Push Image') {
            steps{
          script {
             docker.withRegistry( '', registryCredential ) {
               dockerImage.push("$BUILD_NUMBER")
            }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
        } 
      }
    }
  }
