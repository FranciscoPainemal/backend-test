pipeline {
    agent any
    options {  
        timeout(time:1 , unit:'MINUTES')
    }
    stages('inicio pipeline'){
        steps {
            sh 'echo "Iniciando pipeline"'
        }
        steps {
            sh 'echo "saludos desde jenkins la mitad del pipelina terminal"'
        }
        steps {
            echo 'Adios desde jenkins terminal'
        }
    }
}