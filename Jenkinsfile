pipeline {
    agent any 
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