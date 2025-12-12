pipeline {
    agent {
        docker { image 'node:20' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'npm install && npm run build'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'dist/**'
            }
        }
    }
}
