pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Build Docker') {
            steps {
                script {
                    sh '''
                    echo 'Build Docker Image'
                    docker build -t siva2teja/jenkins:${BUILD_NUMBER} .
                    '''
                }
            }
        }

        stage('Push the artifacts') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerHubCredentials') {
                        sh "docker push siva2teja/jenkins:${BUILD_NUMBER}"
                    }
                }
            }
        }
    }
}
