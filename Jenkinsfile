pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh "docker build -t youssef138/image2:${env.BUILD_NUMBER} ."
            }

        }
        stage('login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'user', passwordVariable: 'pass')]) {
                    sh "docker push youssef138/image2:${env.BUILD_NUMBER}"
                }
            }

        }
    }
}
