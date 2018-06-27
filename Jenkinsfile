pipeline {
	agent any
	stages{
		stage('inicio'){
			steps{
				echo 'Hola mundo'
			}
		}
		stage('pruebas'){
			steps{
				sh 'mvn test'
			}
		}
		stage('build'){
			steps{
				echo 'construyendo el paquete'
			}
		}
		stage('deploy'){
			steps{
				echo 'desplegando el paquete'
			}
		}
	}
}
