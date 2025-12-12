pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Comando real de construcción
                sh 'npm install && npm run build'
            }
        }

        stage('Archive') {
            steps {
                // Publica el artefacto generado
                archiveArtifacts artifacts: 'dist/**'
            }
        }
    }
}
