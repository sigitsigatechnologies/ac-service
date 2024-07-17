pipeline {
    agent any
    tools {
        maven "maven_home"
    }
    stages {
        stage("Build") {
            steps {
                sh "mvn package"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}