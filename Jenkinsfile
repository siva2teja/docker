pipeline {
    agent any

    tools{
        maven "Maven-3.9.6"
    }
    
    stages {
    
        stage('Debugging') {
            steps {
                sh 'ls -l'
            }
        }
        
       stage('Install Nginx') {
            steps {
                sh '''
                /usr/bin/ansible-playbook localhost, nginx.yaml
                '''
            }
        }
    }
}
