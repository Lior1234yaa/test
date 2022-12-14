pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                // add test if file exist
                echo 'Testing..'
                sh "cat mybash.sh"
                sh "ls -a | grep 'mybash.sh'"
            }
        }
        stage('Build') {
            steps {
                // build kit
                echo 'Build....'
                sh "zip target.zip mybash.sh"
                sh "ls -a"
                sh "sudo unzip target.zip -d /var/"
                sh "ls -a"
            }
        }
        stage('DeployToNexsus') {
            steps {
                echo 'Deploy....'
                println "build number:${BUILD_NUMBER}"
            }
        }
        stage('Cd') {
            steps {
                echo 'Cd....'
                // sh "curl -v -u admin:Ly0544209855 http://ec2-18-235-234-126.compute-1.amazonaws.com:8081/repository/maven-public/test/test1/2.0/test1-2.0.zip -L -o MyFilename${BUILD_NUMBER}.zip"
                // sh "ls -a"
            }
        }

    }
}