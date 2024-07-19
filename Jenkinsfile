// pipeline {
//     agent any
//     tools {
//         maven "maven_home"
//     }
//     stages {
//         stage("Build") {
//             steps {
//                 sh "mvn package"
//             }
//         }
//     }
//     post {
//         always {
//             cleanWs()
//         }
//     }
// }
pipeline {
    agent any
    tools {
        maven 'maven_home'
    }
    stages {
        stage ('Initialize') {
            steps {
                container ('maven'){
                    sh '''
                         echo "PATH = ${PATH}"
                         echo "M2_HOME = ${M2_HOME}"
                       '''
                }
            }
        }

        stage ('Build') {
            steps {
                container ('maven'){
                    sh 'mvn -Dmaven.test.failure.ignore=true install'
                }
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
    }
}