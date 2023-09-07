/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'maven:3.9.4-eclipse-temurin-17-alpine' } }
    environment{
        GESCHAFFT = 'Es hat geklappt!'
        FAIL = 'Du doofe Nuss'
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
        }
        success {
            echo "${GESCHAFFT}"
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo "${FAIL}"
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
