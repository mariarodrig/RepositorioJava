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
        bat 'MOVE "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Proyecto-maven\\PruebaDePruebas\\target\\PruebaDePruebas-1.0-SNAPSHOT.war" "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\RepositorioJava_main\\empaquetado"'
      }
    }

  }
}