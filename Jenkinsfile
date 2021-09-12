pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                git url: 'https://github.com/akshitttt/example-voting-app.git'
            }
        }
        stage('Build'){
            steps{
                sh 'docker-compose build'
                sh 'docker-compose up -d'
            }
        }
        stage('SonarQube Analysis'){
            steps{
                script{
                    scannerHome = tool 'Sonarqube';
                }
                withSonarQubeEnv('Sonarqube') {
                sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
