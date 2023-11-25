pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t rajatkokane/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_dUURULOJu_d-0X7k7YVAoULP1ok | /usr/bin/docker login -u rajatkokane --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push rajatkokane/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image rajatkokane/jenkinsdemo --force myservice'
            }
        }

    }
}

