pipeline {
	def app
	stage('Clone') {
		checkout scm
	}
	stage('Build image') { 
		app = docker.build("xavki/nginx") 
	}
	stage('RUN image') {
		docker.image('xavki/nginx').withRun('-p 80:80') {
			sh 'docker ps'  
			sh 'curl localhost'
		}
	}
}
