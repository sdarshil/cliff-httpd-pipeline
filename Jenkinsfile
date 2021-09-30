pipeline {
    agent any

    stages {
        stage('github code') {
            steps {
               git 'https://github.com/sdarshil/cliff-httpd-pipeline'
                
            }
        }
        stage('docker build') {
            steps {
                sh 'docker build .'
                
            } 
        }
        stage('docker push to hub') {
            steps {
                sh 'docker tag newimage sdarshil/clifftest'
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
