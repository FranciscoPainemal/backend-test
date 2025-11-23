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
                sh 'npm rn lint'
            }
        }
        stage('coverage test'){
            steps {
                sh 'echo "Haciendo linter al codigo"'
                sh 'npm rn test:cov'
            }
        }
        stage('build'){
            steps {
                sh 'echo "Haciendo build al codigo"'
                sh 'npm rn build'
            }
        }
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}