pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build' // Add this if you need to run build scripts
            }
        }
    }
}
