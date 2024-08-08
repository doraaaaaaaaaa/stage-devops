pipeline {
    agent any
   
    docker {
        image 'maven:3.8.1-adoptopenjdk-11'
        args '-v /root/.m2:/root/.m2'
    }

    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling ...'
                git branch: 'main',
                    url: 'https://github.com/doraaaaaaaaaa/stage-devops'
                sh 'git branch -a'
                sh 'git status'
            }
        }
        stage('Testing Maven') {
            steps {
                sh 'mvn -version'
            }
        }
        stage('Build') {
        steps {
            sh 'mvn -B -DskipTests clean package'
        }
    }
         stage('Test') {
        steps {
            sh 'mvn test'
        }
        post {
            always {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }   
    }
}
