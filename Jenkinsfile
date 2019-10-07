// Jenkinsfile with new Pull Request
// appending 1 line to test master branch build

@Library('jenkins_shared_libraries_git') _


pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                Build ("./gradlew", "clean build")
            }
        }

        stage('Test') {
            steps {
                Build ("./gradlew", "test")
            }
        }
    }
}
