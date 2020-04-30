pipeline {
    agent any
    
    environment {
        BUILD_DIR = '.'
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Hello World!'
            }
        }
        
        stage('Test') {
            steps {
                echo 'echo "Testing"'
            }
        }
        
        stage('Release') {
            steps {
                echo 'echo Relesed!'
            }
        }
        
        stage('Success') {
            steps {
                echo 'exit 0'
            }
        }
    }
    
    post {
        always {
            echo 'This will always run'
            echo "${BUILD_DIR}"
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
