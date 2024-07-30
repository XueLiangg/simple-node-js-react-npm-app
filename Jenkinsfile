pipeline {
    agent any
    environment {
        PATH = "/usr/local/bin:${env.PATH}"
    }
    stages {
        stage('Build') {
            steps {
                // Display Node.js and npm versions
                sh 'node -v'
                sh 'npm -v'
                // Install npm dependencies
                sh 'npm install'
                // Run build script
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                // Run test script
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                // Run delivery script
                sh './jenkins/scripts/deliver.sh'
                // Pause for user input
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                // Run cleanup script
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}

