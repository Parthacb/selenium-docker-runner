pipeline {
    agent any
    stages {
        stage('Strat Grid') {
              steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }

        stage('Run Test')
        {
            steps{
                bat "docker-compose up search-module book-flight-module"
            }
        }
        stage('Bring Grid Down') {
            steps {
            bat "docker-compose down"

            }
        }
    }
}