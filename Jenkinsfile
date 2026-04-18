pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code is already checked out by Jenkins SCM"
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_TOKEN')]) {
                    sh """
                    mvn clean verify sonar:sonar \
                      -Dsonar.projectKey=java-maven \
                      -Dsonar.projectName='java-maven' \
                      -Dsonar.host.url=http://localhost:9000 \
                      -Dsonar.token=$SONAR_TOKEN
                    """
                }
            }
        }
    }
}