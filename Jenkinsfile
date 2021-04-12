pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {

                git 'https://github.com/ISTQB-Tester-Training/Nexus-Deploy-Release-Test.git'

                sh "mvn deploy"
            }
        }

        stage('Release') {
             steps {
                environment {
                        GITHUB_TOKEN = credentials('GitHub-Token-fuer-jenkins-Zugriff')
                    }
                sh "mvn release:clean release:prepare release:perform -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}"

                   }
             }
        }
    }

