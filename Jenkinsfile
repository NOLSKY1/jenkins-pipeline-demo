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
            -Dsonar.projectKey=ajava-maven-project \
            -Dsonar.projectName=ajava-maven-project \
            -Dsonar.host.url=http://13.69.247.235:9000 \
            -Dsonar.token=${SONAR_TOKEN}
            """
        }
    }
}
    }
}