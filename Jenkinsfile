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
                    sh 'sudo docker-compose -f docker-compose.yaml up --build -d'
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
