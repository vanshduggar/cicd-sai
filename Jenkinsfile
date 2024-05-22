pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo docker compose down"
                sh "sudo docker container prune --force"
                sh "sudo docker image prune --force"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo docker compose -f docker-compose.yml up "
            }
        }
    }
}
