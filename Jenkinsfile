pipeline {
  agent any
  stages {
    stage('verificaci�n de versi�n') {
      parallel {
        stage('verificaci�n de versi�n') {
          steps {
            sh '''mvn --version
git --version
java --version'''
          }
        }

        stage('verificaci�n pom') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('empaquetado war') {
      steps {
        build 'Proyecto-maven'
      }
    }

    stage('crear carpeta') {
      steps {
        sh '''cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace
IF exist empaquetado/nul ( echo empaquetado ya existe ) ELSE ( mkdir empaquetado && echo empaquetado creada)'''
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