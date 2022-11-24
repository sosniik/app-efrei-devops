pipeline {
    tools {
        maven 'maven'
        jdk 'sosnik_JDK'
    }
    agent any
    stages {
        stage("git checkout"){
            steps {
                git credentialsId: 'git_credentials',url:'https://github.com/sosniik/app-efrei-devops.git'
            }
        }
        stage("Build the Application") {
            steps {
                bat "mvn clean install"
            }
        }
        stage('Unit Test Execution') {
            steps{
                bat 'mvn test'
            }
        }
        stage('Build the docker image') {
            steps {
                bat 'docker build -tagsosnik/app-efrei-devops .'
                withCredentials([string(credentialsId: 'dockerhubpass', variable:'dockerHubPass')]){
                    sh "docker login-usosnik -p $dockerHubPass"
                }
                sh 'docker push sosnik/app-efrei-devops'
                sh 'docker scan'
            }
        }

    }
}