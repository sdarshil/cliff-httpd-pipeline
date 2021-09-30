pipeline {
    agent any

    stages {
        
        stage('docker build') {
            steps {
                sh 'sudo docker build . -t sdarshil/clifftest'
                
            } 
        }
        stage('docker push to hub') {
            steps {
                sh 'sudo docker push sdarshil/clifftest'
                
            } 
        }
            stage('kubernetes deploy image set') {
            steps {
                sh 'sudo kubectl set image deployment/production clifftest=sdarshil/clifftest'
                
            } 
        }
        
    }
 }
