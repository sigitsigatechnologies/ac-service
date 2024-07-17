pipeline {
    agent any
    tools {
        maven "maven_home"
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