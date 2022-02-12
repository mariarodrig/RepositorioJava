pipeline {
  agent any
  stages {
    stage('empaquetado war') {
      steps {
        build 'Proyecto-maven'
      }
    }

    stage('crear carpeta') {
      steps {
        bat 'crearCarpeta.BAT'
      }
    }

    stage('mover archivo war') {
      steps {
        sh '''cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Proyecto-maven\\PruebaDePruebas\\target
MOVE PruebaDePruebas-1.0-SNAPSHOT.war "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\empaquetado"'''
      }
    }

  }
}