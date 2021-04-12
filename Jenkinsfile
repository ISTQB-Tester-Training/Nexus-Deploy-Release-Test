pipeline {
    agent any

    environment {
                GITHUB_TOKEN = credentials('GitHub-Token-fuer-jenkins-Zugriff')
    }

    stages {
        stage('Deploy') {
            steps {

                git 'https://github.com/ISTQB-Tester-Training/Nexus-Deploy-Release-Test.git'

                sh "mvn deploy"
            }
        }

        stage('Release') {
             steps {

                sh "mvn release:clean release:prepare release:perform -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}"

                   }
             }
        }
    }

