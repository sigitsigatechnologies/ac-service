pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "source ~/.zsh"
                sh "mvn clean install -Dmaven.test.skip=true"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}