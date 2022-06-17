pipeline {
    agent any

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew test'
            }
        }
//         stage('Test') {
//             steps {
//                 sh './gradlew test'
//             }
//         }
    }
}
