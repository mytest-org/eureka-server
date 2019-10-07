// Jenkinsfile with new Pull Request
// new code

@Library('jenkins-shared-library@master') _

def project = [name: 'eureka-server',
	       githubUrl: 'https://github.com/mytest-org/eureka-server.git',
	       githubCredentialId: '617bab8b-39fe-43f0-a2a6-a82628d85442',
	       githubCommit: '']

/*
node {
	
    triggers {
        githubPullRequest {
            permitAll(true)
            useGitHubHooks(true)
        }
    }
}    // end of node
*/

pipeline {
    agent any

    stages {
        
        stage('Clone repository') {
		
		steps {

//			checkout([$class: 'GitSCM',
//				branches: [[name: "*/${ghprbActualCommit}"]],
//				doGenerateSubmoduleConfigurations: false,
//				extensions: [[$class: 'WipeWorkspace']],
//				submoduleCfg: [],
//                      userRemoteConfigs: [[credentialsId: "${project.githubCredentialId}", url: "${project.githubUrl}", refspec: '+refs/pull/*:refs/remotes/origin/pr/*']]
//			])
echo "dummy step"
			
		} // end of steps

        }    // end of clone stage
        
        stage('build') {
            steps {
                ExecuteGradle ('./gradlew clean build')
            }
        }
    }
}
