pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'set'
                bat 'echo Hello World!'
            }
        }
        
        stage('Test') {
            steps {
                bat 'echo "Testing"'
            }
        }
        
        stage('Release') {
            steps {
                bat 'echo Relesed!'
            }
        }
    }
}
