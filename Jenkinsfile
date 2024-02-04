pipeline {
    agent any

    stages {
        stage("Inicial") {
            steps {
                echo "Iniciando a pipeline"
            }
        }

        stage("Build Docker Image") {
            steps {
                echo "Iniciando processo de construção de imagem docker"
                scripts {
                    docker.build("pgabrieldeveloper/deploy-k8s", "-f Dockerfile.prod .")
                }
                echo "Processo de construção de imagem finalizado"
            }
        }
    }
}