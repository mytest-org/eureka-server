@Library('jenkins-shared-library@master') _

pipeline {
    agent any

    parameters {
        string(name: 'gitlabSourceBranch')
        string(name: 'gitlabTargetBranch')
        string(name: 'gitlabMergeRequestId')
    }
    
    stages {
        stage('build') {
            steps {
                ExecuteGradle ('./gradlew clean build')
            }
        }
    }
}
