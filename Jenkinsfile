// Jenkinsfile with new Pull Request

@Library('jenkins-shared-library@master') _


pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                Build ("./gradle", "clean build")
            }
        }

        stage('Test') {
            Build ("./gradle", "test")
        }
    }
}
