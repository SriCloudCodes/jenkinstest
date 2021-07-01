pipeline {
    agent any    
    environment {
	dockerHome = tool 'mydocker'
        mavenHome  = tool 'mymaven'
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    }
    stages {
        stage ('Build') {
            steps {
		sh 'mvn --version'
		sh 'docker --version'
                echo "Build"
                echo "$PATH"
                echo "BUILD_NUMBER - $env.BUILD_NUMBER"
                echo "BUILD_ID     - $env.BUILD_ID"
                echo "JOB_NAME     - $env.JOB_NAME"
                echo "BUILD_TAG    - $env.BUILD_TAG"
                echo "BUILD_URL    - $env.BUILD_URL"
	
            }
     
        }  
	stage ('Compile') {
   	    steps {
		sh "mvn clean compile"	
        stage (Test'') {
            steps {
                echo "Test"
		echo "------"
		sh " mvn test "
            }
        }  
        stage ('IntTest Build') {
            steps {
                        echo "IntTest Build"
			sh "mvn failsafe:interation-test faisafe:verify"
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
        changed {
            echo "I am in changed  state "
	}
    }
        
}
