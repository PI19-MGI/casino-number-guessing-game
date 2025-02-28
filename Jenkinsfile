pipeline {
    agent any
    triggers {
        pollSCM('*') 
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