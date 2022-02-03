//SCRIPTED

//DECLARATIVE
pipeline {
    agent any
    // agent {docker {image 'maven:3.6.3'} }
    // agent {docker {image 'node:13.8'} }
    stages {
        stage('Build') {
            steps {
                //sh 'mvn --version'
                //sh 'node --version'
                echo "Build"  
                echo "PATH - $PATH"
                echo "BUILD NUMBER - $env.BUILD_NUMBER"
                "BUILD ID - $env.BUILD_ID"
                "JOB NAME - $env.JOB_NAME"
                echo "$env.BUILD_TAG"
                echo "$env.BUILD_URL" 
            }
        }
        stage ('Test') {
            steps {
                echo "Test"
            }
        }
        stage('Interation Test') {
            steps {
                echo "Integration Test"
            }
        }
    }
post {
        always {
            echo 'Im awesome. I read always'
        }
        success {
            echo 'I read when you are successful'
        }
        failure {
           echo 'I read when you fail'
        }
    }
}
