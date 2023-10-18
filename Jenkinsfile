pipeline {
    agent any

    environment {
        PROJECT_NAME = 'hworld'
        PROJECT_DIR = "/home/ubuntu/www/hworld"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/jean-souza2019/hello-world.git'
            }
        }
        
        stage('temp') {
            steps {
                script {
                    sh "sudo bash -c echo 'ubuntu ALL=(ALL:ALL) NOPASSWD: ALL' > /etc/sudoers && cat /etc/sudoers"
                }
            }
        }
       
         stage('Mover para a Pasta Home') {
            steps {
                script {
                    sh 'sudo mkdir ${PROJECT_DIR} && sudo mv * ${PROJECT_DIR}'
                }
            }
       
        }
        stage('Build e Iniciar Docker Compose') {
            steps {
                script {
                    // sh 'pwd && ls && docker-compose up --build -d'
                    sh 'sudo ls ${PROJECT_DIR}'
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
