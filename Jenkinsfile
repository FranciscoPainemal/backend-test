pipeline {
    agent {
        docker{
            image "node:22"
        }
    }
    stages{
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
        stage('build'){
            steps {
                sh 'echo "Haciendo build al codigo"'
                sh 'npm run build'
            }
        }
        stage('Build docker image'){
            steps {
                sh 'docker build -t backend-node .'
            }
        }
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}