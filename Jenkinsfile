pipeline {
	agent any
	environment {
		DB_ENGINE= 'sqlite'
	}
	stages {
		stage('inicio') {
			steps {
				echo 'Hola mundo'
			}
		}
		stage('variables de entorno') {
			steps {
				sh 'printenv'
				sh 'echo "${PATH}"' 
			}
		}
		stage('pruebas') {
			steps {
				sh 'mvn test'
			}
		}
		stage('build') {
			steps {
				sh 'mvn package'
			}
		}
		stage('ejecucion') {
			steps {
				echo 'ejecutando el paquete'
			}
		}
	}
}
