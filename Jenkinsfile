node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build('msaddamhussain07/example-app')
	}

	stage('Push image') {
		docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
			app.push('latest')
		}
	}
}
