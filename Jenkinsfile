@Library('jenkins-shared-library@master') _

//def project = [name: 'eureka-server', githubUrl: 'https://github.com/mytest-org/eureka-server.git', githubCredentialId: '', githubCommit: '']

def project.name = 'eureka-server'
def project.githubUrl = 'https://github.com/mytest-org/eureka-server.git'
def project.githubCredentialId = '617bab8b-39fe-43f0-a2a6-a82628d85442'
def project.githubCommit = ''

pipeline {
    agent any
    
    triggers {
        githubPullRequest {
            permitAll(true)
            useGitHubHooks(true)
        }
    }
    
    stages {
        
        stage('Clone repository') {

			checkout([$class: 'GitSCM',
				branches: [[name: "*/${ghprbActualCommit}"]],
				doGenerateSubmoduleConfigurations: false,
				extensions: [[$class: 'WipeWorkspace']],
				submoduleCfg: [],
                      userRemoteConfigs: [[credentialsId: "${project.githubCredentialId}", url: "${project.githubUrl", refspec: '+refs/pull/*:refs/remotes/origin/pr/*']]
			])


        }    // end of clone stage
        
        stage('build') {
            steps {
                ExecuteGradle ('./gradlew clean build')
            }
        }
    }
}
