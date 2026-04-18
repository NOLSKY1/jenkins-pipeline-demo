pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build + SonarQube Analysis') {
            steps {
                withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_TOKEN')]) {
                    sh '''
                    mvn clean verify sonar:sonar \
                      -Dsonar.projectKey=java-maven \
                      -Dsonar.projectName=java-maven \
                      -Dsonar.host.url=http://192.168.146.132:9000 \
                      -Dsonar.login=$SONAR_TOKEN
                    '''
                }
            }
        }

    }
}