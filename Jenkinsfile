pipeline {
    agent any
    
    tools {
        maven 'Maven' 
    }
       
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/Mckins-B/Scandic-Task.git', branch: 'master'
            }
        }
        
        stage('Validate') {
            steps {
                sh 'mvn validate'
            }
        }
        
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    
    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed! Check logs for details.'
        }
    }
}
