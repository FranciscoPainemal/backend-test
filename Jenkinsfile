pipeline {
    agent any
    stages{
        stage("Procesando app NodeJS"){
            agent{
                docker{
                    image "node:22"
                }
            }
            stages {
                stage('inicio pipeline'){
                    steps {
                        sh 'echo "Iniciando pipeline"'
                    }
                }
                stage('Dependencias'){
                    steps {
                        sh 'echo "mitad de pipielin"'
                        sh 'npm install'
                    }
                }
                stage('Lint codigo'){
                    steps {
                        sh 'echo "Haciendo linter al codigo"'
                        sh 'npm run lint'
                    }
                }
                stage('coverage test'){
                    steps {
                        sh 'echo "Haciendo linter al codigo"'
                        sh 'npm run test:cov'
                    }
                }
                stage('Ejecutando build'){
                    steps {
                        sh 'echo "Haciendo build al codigo"'
                        sh 'npm run build'
                    }
                }
            }
        }
        stage('Build docker image'){
            steps {
                sh 'docker build -t backend-test .'
                sh 'docker tag backend-test wainerock/backend-test'
                sh "docker tag backend-test wainerock/backend-test:${env.BUILD_NUMBER}"
                
                script{
                    docker.withRegistry("https://index.docker.io/v1/", "id-credencial-jenkins"){
                        sh 'docker push wainerock/backend-test'
                        sh "docker push wainerock/backend-test:${env.BUILD_NUMBER}"
                    }
                }
                docker.withRegistry("https://ghcr.io","credencial-github"){
                        sh 'docker tag backend-test ghcr.io/FranciscoPainemal/backend-test'
                        sh "docker tag backend-test ghcr.io/FranciscoPainemal/backend-test:${env.BUILD_NUMBER}"
                        sh 'docker push ghcr.io/FranciscoPainemal/backend-test'
                        sh "docker push ghcr.io/FranciscoPainemal/backend-test:${env.BUILD_NUMBER}"
                }
            }
        }
        stage('Despliegue continuo'){
            agent{
                docker{
                    image 'alpine/k8s:1.32.2'
                    reuseNode true
                }
            }
            steps{
                withKubeConfig([credentialsId: 'kubeconfig-docker']){
                    sh "kubectl -n backend-test set image deployments backend-dp bakcend=localhost:8082/backend-test-devops:#{BUILD_NUMBER}"
                }
            }
        }
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}