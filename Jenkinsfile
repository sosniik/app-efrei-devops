pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  environment {
     couleur = "bleu"
     utilisateur = "Leo"
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
    environment {
         loisir = "Skate"
         couleur = "Rouge"
      }
     steps {
       echo "La couleur est ${couleur} pour l'utilisateur ${utilisateur}"
       echo "${loisir}"
       echo "${couleur}"
     }
    }

  }

}