pipeline {
	agent any
	stages {
		stage('Welcome') {
			steps {
				echo 'Hi, you are inside the pipeline'
				}
			}	
		stage('Giving permission') {
			steps {
				sh 'chmod +x build.sh'
				}
			}
		stage('build') {
			steps {
				sh './build.sh'
				}
			}	
		stage('image push to docker hub') {
			steps {
				script {
					sh 'docker login -u anandxmech -p Anand@123'
					sh 'docker push anandxmech/dev:capstone'
					}
				}
			}
		stage('deployment') {
			steps {
				script {
					sh 'chmod +x deploy.sh'
					sh './deploy.sh'
					}
				}
			}
		}
	}
