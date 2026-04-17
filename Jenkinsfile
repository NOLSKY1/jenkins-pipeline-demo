pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/NOLSKY1/jenkins-pipeline-demo.git',
                credentialsId: 'github-cred'
            }
        }

        stage('Sonar Test') {
            steps {
                sh '''
                echo "Running Sonar test..."
                mvn sonar:sonar \
                -Dsonar.projectKey=test-project \
                -Dsonar.host.url=http://localhost:9000 \
                -Dsonar.login=wrong-token
                '''
            }
        }
    }
}