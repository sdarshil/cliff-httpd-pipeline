pipeline {
    agent any

    stages {
        
        stage('docker build') {
            steps {
                sh 'sudo docker build . -t sdarshil/clifftest:$BUILD_NUMBER'
                
            } 
        }
        stage('docker push to hub') {
            steps {
                sh 'sudo docker push sdarshil/clifftest:$BUILD_NUMBER'
                
            } 
        }
            stage('kubernetes deploy image set') {
            steps {
                sh 'sudo kubectl set image deployment/production clifftest=sdarshil/clifftest:$BUILD_NUMBER'
                
            } 
        }
        
    }
 }
