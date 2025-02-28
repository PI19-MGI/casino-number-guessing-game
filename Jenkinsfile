pipeline {
    agent any
    triggers {
        pollSCM('H/5 * * * *')  // Polls every 5 minutes (adjust as needed)
    }
    stages {
        stage('Build') { 
            when { 
                branch 'main'  // Ensures it runs only for the main branch
            }
            steps {
                sh 'rm -rf build'
                sh 'cmake -B build -S .' 
                sh 'cmake --build build'
            }
        }
    }
}