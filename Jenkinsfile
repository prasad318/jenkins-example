pipeline {
	agent {  label 'jenkins-slave1' }
	stages {
		stage('---clean----'){
			tools {
				maven 'maven_3.9.0'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		}
		stage('---test---') {
			tools {
				maven 'maven_3.8.6'
			}
			steps {
				sh 'mvn --version'
				sh "mvn test"
			}
		}
		stage('---package---'){
			
			steps {
				sh "mvn package"
			}
		}
	}
	post {
		success {
			echo 'job was built successfully'
		}
		failure {
			echo 'job was not build..it was failed'
		}
	}
}
