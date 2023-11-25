```groovy

pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t shnk/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_eB-g-nh0WP5R_EiJ7gKVISmne38 | /usr/bin/docker login -u shnk --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push shnk/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image shnk/jenkinsdemo --force myservice'
            }
        }

    }
}

```
