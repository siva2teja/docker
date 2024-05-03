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
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
      stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t siva2teja/jekins:${BUILD_NUMBER} .
                    '''
                }
            }
        }

        stage('Push the artifacts'){
           steps{
                script{
                    sh '''
                    echo 'Push to Repo'
                    docker login -u siva2teja --password-stdin dckr_pat_bqdT-ndJx3HktTnaeQJipT5ifHM
                    docker push siva2teja/jekins:${BUILD_NUMBER}
                    '''
                }
            }
        }
     
    }
}
