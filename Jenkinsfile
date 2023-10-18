pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/jean-souza2019/hello-world.git'
            }
        }
       
        stage('Build e Iniciar Docker Compose') {
            steps {
                script {
                    sh 'docker-compose up --build -d'
                    // sh 'ls && pwd'
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
