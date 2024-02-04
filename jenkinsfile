pipeline = {
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
                    dockerapp = docker.build("pgabrieldeveloper/deployDockerfile", "-f Dockerfile.prod ." )
                }
                echo "Processo de construção de imagem finalizado"
            }
        }
    }
}