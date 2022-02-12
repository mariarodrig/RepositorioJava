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
        bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace'
        bat 'IF exist empaquetado/nul ( echo empaquetado ya existe ) ELSE ( mkdir empaquetado && echo empaquetado creada)'
      }
    }

    stage('mover archivo war') {
      steps {
        bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Proyecto-maven\\PruebaDePruebas\\target'
        bat 'MOVE PruebaDePruebas-1.0-SNAPSHOT.war "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\empaquetado"'
      }
    }

  }
}