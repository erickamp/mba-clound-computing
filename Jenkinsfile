pipeline {
    agent any 
     tools { 
        nodejs "node 18.17.0" 
    }    
    stages {
        stage('Checkout') {
            
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/erickamp/mba-clound-computing.git']]])
            }
        
        stage('Build') {
            steps {
                bat "node -v"
                bat 'npm install'
                bat 'npm run build'
            }
        }
        
        stage('Run Unit Tests') {
            steps {
                bat 'npm run test'
            }
        }            
            
        }
    }
}
