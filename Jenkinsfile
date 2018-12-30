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
            }
        }
        stage('Test') { 
            steps {
                echo 'Test' 
                sh 'mvn clean package stylechecklist:stylechecklist'
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Deployl' 
            }
        }
    }
}