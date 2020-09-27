pipeline {
    agent any
    stages {

        stage('Pull Latest Image'){
            steps{
                bat "docker pull partha59docker/selenium-docker"
            }
        }
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
    }

    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            bat "docker-compose down"
        }
    }
}