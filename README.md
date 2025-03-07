pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mvn clean package' // Example for a Java project
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test' 
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'scp target/myapp.jar user@server:/path/to/deploy'
            }
        }
    }
}
# Jenkinsfile
