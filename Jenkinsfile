pipeline {
    agent {
        docker{
            image node:22
        }
    }
    options {  
        timeout(time:1 , unit:'MINUTES')
    }
    stages{
        stage('inicio pipeline'){
            steps {
                sh 'echo "Iniciando pipeline"'
            }
        }
        stage('MItad PIpeline'){
            steps {
                echo 'mitad de pipielin'
            }
        }
        stage('Dependencias'){
            steps {
                sh 'echo "mitad de pipielin"'
                sh 'npm install'
            }
        }
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}