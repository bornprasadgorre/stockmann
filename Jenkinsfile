pipeline {
	agent any
stages {
    stage('Git Preparation'){
    steps {
        script {
	    sh "git config --global user.email prasad.gorre@borngroup.com"
        sh "git config --global user.name bornprasadgorre"
        sh 'git config --global credential.helper cache'
		sh "rm -rf ${WORKSPACE}/*"
		}
		}
    }
	stage('Git Clone'){
        steps {	
            script {
		        sh 'git clone git@github.com:bornprasadgorre/stockmann.git'
            }
		}
	 }

	stage('Git Available Branches list'){
        steps {	
            script{
                sh 'git branch -a'
            }
		}
	 }

	stage('Git committerdate list'){
        steps {	
            script{
                sh "git for-each-ref --sort=committerdate refs/heads/ --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(color:red)%(objectname:short)%(color:reset) - %(contents:subject) - %(authorname) (%(color:green)%(committerdate)%(color:reset))'"
            }
		}
	 }
    }
}
