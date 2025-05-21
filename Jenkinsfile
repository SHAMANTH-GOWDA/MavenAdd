pipeline {
    agent any  // Use any available agent

    tools {
    maven 'Maven'  // Use the name exactly as configured in Jenkins
}

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/SHAMANTH-GOWDA/MavenAdd.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar target/MavenAdd-1.0-SNAPSHOT.jar'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
