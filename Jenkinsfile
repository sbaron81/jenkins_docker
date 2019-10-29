pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-docker-whale -f Dockerfile .'
            }
        }
        stage('Docker run') {
            steps {
                sh 'docker container ls | grep my-whale && docker container rm -f my-whale'
                sh 'docker run --name my-whale my-docker-whale'
            }
        }
    }
}

