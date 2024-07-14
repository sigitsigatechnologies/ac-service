pipline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "mvn version "
                sh "mvn clean install -Dmaven.test.skip=true"
            }
        }
    }

    post {
        always {
            cleanWS()
        }
    }
}