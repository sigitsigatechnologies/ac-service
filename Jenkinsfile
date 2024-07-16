pipeline {
    agent any
    tools {
        maven 'Maven 3.8.6'
        jdk 'Java 11.0.7'
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