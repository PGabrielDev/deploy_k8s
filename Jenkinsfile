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
                script {
                    def dockerImage = docker.build("pgabrieldeveloper/deploy-k8s:${env.BUILD_ID}", "-f Dockerfile.prod .")
                }
                echo "Build finalizado"
            }
        }
        stage("Push Docker Image"){
            steps {
                echo "Inicando processo de push de imagem"
                script {
                    docker.withRegistry("https://registry.hub.docker.com", "dockerhub") {
                        dockerImage.push("latest")
                        ockerImage.push(${env.BUILD_ID})
                    }
                }
                echo "Push finalizado"
            }
        }
    }
}

