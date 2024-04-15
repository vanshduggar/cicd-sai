pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Install dependencies and build the React project
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
        
        stage('Deploy') {
            environment {
                IMAGE = 'saicharan'
            }
            steps {
                script {
                    // Build Docker image
                    sh "docker build -t $IMAGE ."
                    
                    // Push Docker image to a registry (optional)
                    sh "docker push $IMAGE"
                    
                    // Run Docker container
                    sh "docker run -d -p 80:80 $IMAGE"
                }
            }
        }
    }
}
