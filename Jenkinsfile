pipeline {
    agent any
    options{
        timeout(time:1 , unit: 'MINUTES')
    }
    stages('inicio pipeline'){
        steps {
            sh 'echo "Iniciando pipeline"'
        }
    }
    stages('mitad pipelina'){
        steps {
            sh 'echo "saludos desde jenkins la mitad del pipelina terminal"'
        }
    }
    stages('Finalizando pipeline'){
        steps {
            echo 'Adios desde jenkins terminal'
        }
    }
}