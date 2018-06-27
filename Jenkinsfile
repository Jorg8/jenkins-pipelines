pipeline {
	agent any
	environment {
		DB_ENGINE= 'sqlite'
	}
	tools {
		maven 'maven'
	}
	stages {
		stage('Inicio') {
			steps {
				echo 'Hola mundo'
			}
		}
		stage('¿Dónde está maven?') {
			steps {
				sh 'echo "${MAVEN_HOME}"' 
			}
		}
		stage('Variables de entorno') {
			steps {
				sh 'printenv'
				sh 'echo "${PATH}"' 
			}
		}
		stage('Pruebas') {
			steps {
				echo 'Ejecutando pruebas unitarias del proyecto'
				sh 'mvn test'
				junit(allowEmptyResults: true, testResults:'**/target/surefire-reports/*.xml')
			}
		}
		stage('Empaquetado') {
			steps {
				echo 'Empaquetando la aplicación'
				sh 'mvn package'
			}
		}
		stage('Ejecución') {
			steps {
				echo 'Ejecutando el paquete'
				sh 'mvn exec:java -Dexec.mainClass="com.pipeline.test.App"'
			}
		}
	}
}
