node {

    stage('Build Image') {
        sh 'docker build --no-cache -t mynginx .'
    }

    stage('Run Container') {
        sh 'docker rm -f mycontainer || true'
        sh 'docker run -d -p 80:80 --name mycontainer mynginx'
    }

    stage('Verify Deployment') {
        sh 'docker ps'
        echo 'Deployment successful!'
    }
}
