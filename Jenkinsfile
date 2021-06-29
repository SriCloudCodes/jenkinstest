pipeline {
    agent any    
    stages {
        stage ('Build') {
            steps {
                echo "Build"
            }
        }  
        stage ('Test') {
            steps {
                echo "Test"
            }
        }  
        stage ('IntTest Build') {
            steps {
                        echo "IntTest Build"
            }
        }  
   
    }

    post {
        always {
            echo "I am always successful"
	}
        success {
            echo "I am  successful only in Success"
	}
        failure {
            echo "I am in Failed state "
	}

    }
        
}
