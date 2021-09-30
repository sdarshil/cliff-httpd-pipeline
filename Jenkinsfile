pipeline {
    agent any

    stages {
        
        stage('docker build') {
            steps {
                sh 'docker build . -t sdarshil/clifftest'
                
            } 
        }
        stage('docker push to hub') {
            steps {
                sh 'docker push sdarshil/clifftest'
                
            } 
        }
            stage('kubernetes deploy image set') {
            steps {
                sh 'kubectl set image deployment/production clifftest=sdarshil/clifftest'
                
            } 
        }
        
    }
 }
