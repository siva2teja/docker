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
        
    }
     stage('Install Nginx') {
            steps {
                sh '''
                ansible-playbook -i inventory install_nginx.yaml
                '''
            }
        }
}
