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
        stage {
            steps {
                sh 'echo "saludos desde jenkins la mitad del pipelina terminal"'
            }
        }
        stage {
            steps {
                echo 'Adios desde jenkins terminal'
            }
        }
    }
}