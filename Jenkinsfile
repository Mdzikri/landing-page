pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    cleanWs() //Bersihin data sebelum clone
                    checkout scmGit(userRemoteConfigs: [
                        [ url: 'https://github.com/Mdzikri/landing-page' ]
                    ])
                }
            }
        }
        stage('Build') {
            steps {
                script {  
                    sh "docker build -t giovana02/bebas:1.1.1 ."
                }
            }
        }
        stage('Deploy') {
            steps {
                script {  
                    sh "docker push giovana02/bebas:1.1.1"
                }
            }
        }
    }
}
