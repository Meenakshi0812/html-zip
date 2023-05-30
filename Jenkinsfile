pipeline {
    agent any

    stages {
        stage('Pull and Zip Code') {
            steps {
                sh "cd /home/ubuntu && git clone https://github.com/Meenakshi0812/html-zip.git"
                sh "cd /home/ubuntu/html-zip && zip -r code_`date +%Y%m%d%H%M%S`.zip ./*"
            }
        }

        stage('Copy Zip and Unzip') {
            steps {
                sh 'cp /home/ubuntu/html-zip/code*.zip /var/www/html/'
                sh 'unzip /var/www/html/*.zip -d /var/www/html/'
            }
        }

        stage('Create Soft Link') {
            steps {
                sh 'ln -s /var/www/html/*.zip /var/www/html/application'
            }
        }
    }
}
