pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/jean-souza2019/hello-world.git'
            }
        }

        stage('Mover para Pasta Específica') {
            steps {
                sh 'mv * /home/ubuntu/www'
            }
        }
        stage('finishing') {
            steps {
                echo 'deploy completed'
            }
        }
    }

    // post {
    //     always {
    //         // Limpeza ou ações pós-conclusão, se necessário
    //     }
    // }
}
