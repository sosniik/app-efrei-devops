pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  stages {
    stage('Lister les étapes') {
      steps {

        sh '''

          java -version

        '''

      }
    }
    stage('Utilisation des variables') {
     steps {
       echo "BUILD_NUMBER = ${env.UTILISATEUR}"
     }
    }

  }

}