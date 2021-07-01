pipeline {
    agent any    
    environment {
	dockerHome = tool 'mydocker'
        mavenHome  = tool "mymaven"
    stages {
        stage ('Build') {
            steps {
                echo "Build"
                echo "$PATH"
                echo "BUILD_NUMBER - $env.BUILD_NUMBER"
                echo "BUILD_ID     - $env.BUILD_ID"
                echo "JOB_NAME     - $env.JOB_NAME"
                echo "BUILD_TAG    - $env.BUILD_TAG"
                echo "BUILD_URL    - $env.BUILD_URL"

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
