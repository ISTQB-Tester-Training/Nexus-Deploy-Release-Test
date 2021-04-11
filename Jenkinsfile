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

                sh "mvn Release:Clean release:prepare release:perform -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}"

                   }
             }
        }
    }
}