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
                    sh 'pwd && ls && sudo docker-compose up --build -d'
                    // sh 'sudo docker ps'
                }
            }
        }
    }

    // post {
    //     always {
    //         deleteDir()
    //     }
    // }
}
