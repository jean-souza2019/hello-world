pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/jean-souza2019/hello-world.git'
            }
        }
       
         stage('Mover para a Pasta Home') {
            steps {
                script {
                    sh 'mv * ~/'
                }
            }
        }
       
        stage('Build e Iniciar Docker Compose') {
            steps {
                script {
                    // sh 'pwd && ls && docker-compose up --build -d'
                    sh 'ls ~/'
                }
            }
        }
    }

    post {
        always {
            deleteDir()
        }
    }
}
