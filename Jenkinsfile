pipeline {
    agent any
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
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}