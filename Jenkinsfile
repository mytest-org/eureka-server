// Jenkinsfile with new Pull Request

@Library('jenkins-shared-library_git@master') _


pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                Build ("./gradle", "clean build")
            }
        }

        stage('Test') {
            steps {
                Build ("./gradle", "test")
            }
        }
    }
}
