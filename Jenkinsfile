pipeline {
    agent any
    
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }

    stages {
         stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'
            }
        }
    }
}

