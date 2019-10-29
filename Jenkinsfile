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
        stage('Docker clean') {
                steps {
                    sh(returnStdout: true, script: 'docker container rm -f my-whale || echo Ok')
                }
        }
        stage('Docker run') {
            steps {
                sh 'docker run --name my-whale my-docker-whale'
            }
        }
    }
}

