pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  environment {
     couleur = "bleu"
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
       sh 'printenv'
     }
    }

  }

}