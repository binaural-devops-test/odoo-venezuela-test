pipeline {
    agent any

    environment {
        IS_INTEGRA_FORK = credentials('GITHUB_REPO_ENV_IS_INTEGRA_FORK') // Obtiene variable desde GitHub API o Jenkins
    }

    stages {
        stage('Validar condición') {
            when {
                expression { env.IS_INTEGRA_FORK == 'TRUE' }
            }
            steps {
                echo "Ejecutando pipeline para repositorio con IS_INTEGRA_FORK=TRUE"
            }
        }

        stage('Build PR') {
            steps {
                echo "Construyendo Pull Request..."
                // Aquí agregas tu lógica de CI/CD
            }
        }
    }

    post {
        success {
            echo "Pipeline ejecutado con éxito para este PR."
        }
        failure {
            echo "Falló la ejecución, revisa los logs."
        }
    }
}
