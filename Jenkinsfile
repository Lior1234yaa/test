pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                // add test if file exist
                echo 'Testing..'
                sh "cat mybash.sh"
                sh "ls -a | grep 'dddd.sh'"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}