pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                sh 'docker build --no-cache -t mynginx .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
                sh 'docker run -d -p 80:80 --name mycontainer mynginx'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'docker ps'
                echo 'Deployment successful!'
            }
        }
    }
}git