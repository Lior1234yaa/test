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
                sh "rm -rf mybash.sh"
            }
        }
        stage('DeployToNexsus') {
            steps {
                // can't
                echo 'Deploy....'
                println "build number:${BUILD_NUMBER}"
            }
        }
        stage('Cd') {
            steps {
                echo 'Cd....'
                sh "curl -v -u admin:Ly0544209855 http://ec2-18-235-234-126.compute-1.amazonaws.com:8081/repository/maven-public/mytest/test/1.0/test-1.0.zip -L -o target${BUILD_NUMBER}.zip"
                sh "ls -a"
                sh "unzip target${BUILD_NUMBER}.zip"
                sh "chmod +x -R ${env.WORKSPACE}"
                sh "./mybash.sh"
            }
        }
        stage('clean') {
            steps {
                cleanWs();
            }
        }

    }
}