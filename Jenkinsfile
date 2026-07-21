pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'github-pat', url: 'https://github.com/Parimal-Pradhan/website-deployment.git'
            }
        }

        stage('Build') {
            steps {
                echo "Build Started"

                sh '''
                ls -la
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing HTML"

                sh '''
                if [ -f index.html ]; then
                    echo "HTML Found"
                else
                    echo "No HTML"
                    exit 1
                fi
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                     cp -r * /var/www/html/
                 '''
            }
        }

    }

}
