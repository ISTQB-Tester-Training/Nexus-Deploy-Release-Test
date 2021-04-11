pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {

                git 'https://github.com/ISTQB-Tester-Training/Nexus-Deploy-Release-Test.git'

                sh "mvn deploy"
            }
        }
    }
}