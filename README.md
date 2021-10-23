pipeline {
    agent none 
    stages {
        stage('Example Build') {
            agent { docker 'nginx' } 
            steps {
                echo 'Hello, nginx'
                sh 'nginx --version'
            }
        }
        stage('Example Test') {
            agent { docker 'ubuntu' } 
            steps {
                echo 'Hello, ubi'
                sh 'ubuntu -version'
            }
        }
         stage('Example Test') {
            agent { docker 'centos:6' } 
            steps {
                echo 'Hello, centos'
                sh 'centos -version'
         }
     }
  }
}
