pipeline {
    agent none 
    stages {
        stage('Example Build') {
            agent { docker 'centos:8' } 
            steps {
                echo 'Hello, centos'
            }
        }
        stage('Example Test') {
            agent { docker 'ubuntu' } 
            steps {
                echo 'Hello, ubi'
            }
        }
         stage('Deploy') {
            agent { docker 'centos:6' } 
            steps {
                echo 'Hello, centos'
         }
     }
  }
}
