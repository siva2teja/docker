pipeline {
    agent any

    tools{
        maven "Maven-3.9.6"
    }
    
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Debugging') {
            steps {
                sh 'ls -l'
            }
        }
        
       stage('Install Nginx') {
            steps {
                sh '''
                /usr/bin/ansible-playbook -i inventory nginx.yaml
                '''
            }
        }
    }
}
