pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "cat mybash.sh"
                sh "ls -a | grep 'mybash.sh'"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}