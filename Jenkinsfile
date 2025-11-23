pipeline {
    agent any
    options {  
        timeout(time:1 , unit:'MINUTES')
    }
    stages{
        stage {
            sh 'echo "Iniciando pipeline"'
        }
        stage {
            sh 'echo "saludos desde jenkins la mitad del pipelina terminal"'
        }
        stage {
            echo 'Adios desde jenkins terminal'
        }
    }
}