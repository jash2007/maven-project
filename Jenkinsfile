pipeline {
    agent any 
    tools {
maven 'MAVEN'
jdk 'JDK'
    } 
    
    stages {
        stage('Build') { 
            steps {
                echo 'Build' 
                 sh 'mvn clean package checkstyle:checkstyle'
            }
            post {
                success {
                    echo "This is checkstyle line"
                    checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
                    echo "This is archive artifacts"
                    archive '**/*.war'
                    echo "Java here"
                    junit '**/target/surefire-reports/*.xml'
                }
            }

        }
        stage('Test') { 
            steps {
                echo 'Test' 
               
            }
        }
        stage('Deploy') { 
            steps {
                timeout(3) {
                             input 'Do you really want to proceed?'
                            }       
                                echo 'Deployment' 
                                 build 'Job-Deploy'
            }
        }
    }
}