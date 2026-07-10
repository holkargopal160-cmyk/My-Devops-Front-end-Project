cat << 'EOF' > Jenkinsfile 
pipeline {
    agent any

    stages {
        stage('Docker Build') {
            steps {
                sh 'docker build -t my-frontend-image:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop my-frontend-app || true'
                sh 'docker rm my-frontend-app || true'
                sh 'docker run -d --name my frontend-app -p 8081:80 my-frontend-image:latest'
            }
        }
    }

}
EOF