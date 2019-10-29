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
                sh 'echo docker run'
            }
        }
    }
}

