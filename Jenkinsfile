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
        
        // stage('temp') {
        //     steps {
        //         script {
        //             sh  'sudo echo -e "12345\n12345" | sudo passwd jenkins'
        //         }
        //     }
        // }
       
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
                    sh 'sudo chmod -R 777 ${PROJECT_DIR} && sudo docker-compose -f ${PROJECT_DIR}/docker-compose.yml up --build -d'
                    // sh 'sudo ls ${PROJECT_DIR}'
                }
            }
        }
    }

    post {
        always {
            deleteDir()
            script {
                sh 'sudo rm -rf ${PROJECT_DIR}'
            }
        }
        success {
            script {
                sh 'sucesso'
            }
        }
        failure {
            script {
                sh 'falha'
            }
        }
    }
}
