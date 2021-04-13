pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {

                git 'https://github.com/ISTQB-Tester-Training/Nexus-Deploy-Release-Test.git'

                sh "mvn package org.sonatype.plugins:nexus-staging-maven-plugin:deploy -DskipTests"
            }
        }

        stage('Release') {

             environment {

                GITHUB_TOKEN = credentials('GitHub-Token-fuer-jenkins-Zugriff')

             }

             steps {

                sh "mvn release:clean release:prepare release:perform -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}"

             }
        }
    }
}
