pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Paso para clonar el repositorio
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Paso para compilar tu aplicación
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Paso para ejecutar pruebas
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Paso para desplegar en Azure
                    sh 'az webapp deploy --name <nombre_aplicacion> --resource-group <nombre_grupo_recursos> --src-path <ruta_paquete>'
                }
            }
        }
    }
}
