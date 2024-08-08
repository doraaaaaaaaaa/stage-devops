pipeline {
    agent any
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
    }
}
