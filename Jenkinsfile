// Jenkinsfile with new Pull Request

@Library('jenkins_shared_libraries_git') _


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
