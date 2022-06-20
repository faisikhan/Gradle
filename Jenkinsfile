pipeline {
    agent any
 stages {
    stage('Clone Git') {
      steps {
        git([url: 'git@github.com:faisikhan/gradle.git', credentialsId: 'githubcreds', branch: 'master'])
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew'
            }
        }
    }
  }
 }
}
