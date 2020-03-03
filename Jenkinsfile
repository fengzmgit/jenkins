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
        
        stage('Fail') {
            steps {
                bat 'exit 1'
            }
        }
    }
    
    post {
        always {
            echo 'This will always run'
            junit 'build/reports/**/*.xml'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
            
            mail to: 'fengzm@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
            
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
