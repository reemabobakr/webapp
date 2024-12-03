pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr html'
                sh 'git clone https://github.com/reemabobakr/webapp.git'
            }
        }
        stage('push repo to remote host') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh -i /home/reem/Downloads/remote-key.pem ubuntu@16.170.146.46 sudo git -C /var/www/html pull'
            }
        }
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                // sh 'curl -Is 16.170.146.46 | head -n 1'
                curl -Is --max-time 30 16.170.146.46 | head -n 1

            }
        }
    }
}
