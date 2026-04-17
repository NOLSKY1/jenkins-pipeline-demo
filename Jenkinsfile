pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code is already checked out by Jenkins SCM"
            }
        }

        stage('Test') {
            steps {
                sh 'echo Hello Jenkins is working'
            }
        }
    }
}