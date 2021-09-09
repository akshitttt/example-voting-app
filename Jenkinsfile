pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                git url: 'https://github.com/akshitttt/example-voting-app.git'
            }
        }
        stage('Build-Docker'){
          steps{
                sh "docker-compose build"
                sh "docker-compose up -d"
            }
        }
    }
}
