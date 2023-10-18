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
                    sh 'sudo mv * /home/ubuntu/www'
                }
            }
        }
       
        stage('Build e Iniciar Docker Compose') {
            steps {
                script {
                    // sh 'pwd && ls && docker-compose up --build -d'
                    sh 'sudo ls /home/ubuntu/www'
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
