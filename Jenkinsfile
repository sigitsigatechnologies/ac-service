pipeline {
    agent any
    tools {
        maven 'Maven 3.9.8'
    }
    stages {
        stage("Build") {
            steps {
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