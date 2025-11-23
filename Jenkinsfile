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
        stage('FIn PIpeline'){
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}