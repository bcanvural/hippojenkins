pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }

    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean verify'
                sh 'mvn -Pdist'
            }
        }
        stage('Test') {
            steps {
                sh 'bash ./jenkins/scripts/verify.sh'
            }
        }
    }
}