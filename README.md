pipeline {
    agent none 
    stages {
        stage('Example Build') {
            agent { docker 'centos:8' } 
            steps {
                echo 'Hello, centos'
                sh 'pwd'
            }
        }
        stage('Example Test') {
            agent { docker 'centos:8' } 
            steps {
                echo 'Hello, ubi'
                sh 'time'
            }
        }
         stage('Deploy') {
            agent { docker 'centos:8' } 
            steps {
                echo 'Hello, centos'
                sh 'ls'
         }
     }
  }
}
