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
	stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'kitty-sonar-scanner'
            }
            steps {
                withSonarQubeEnv('kitty-trends-sonarqube-server'){
			 sh '${scannerHome}/bin/sonar-scanner'
		}
            }
        }
    }
}

