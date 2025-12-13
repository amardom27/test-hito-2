pipeline {
    agent any

    environment {
        PATH = "/home/usuario/.nvm/versions/node/v25.2.1/bin:$PATH"
    }
    
    stages {
        stage('Verify npm and node') {
            steps {
                echo 'Verifying tools...'
                sh 'node -v'
                sh 'npm -v'
            }
        }
        
        stage('Install') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Making the build...'
                sh 'npm run build'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
            }
        }
    }
}
