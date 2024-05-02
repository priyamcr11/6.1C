pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Delay') {
            steps {
                // Add a delay of 1 minute (60 seconds)
                sleep time: 60, unit: 'SECONDS'
            }
        }
        stage('Build') {
            steps {
                // Build the code using Maven
                echo "Building the code using Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests using JUnit or TestNG
                // Run integration tests using a tool like Selenium or Postman
                echo "Running Unit and Integration Tests using JUnit and Selenium"
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate a code analysis tool like SonarQube
                echo "Running code analysis using SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                // Perform security scan using a tool like OWASP ZAP or SonarQube
                echo "Performing security scan using SonarQube"
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy the application to staging server (e.g., AWS EC2)
                echo "Deploying to staging server AWS EC2"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
                echo "Running integration tests on staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy the application to production server (e.g., AWS EC2)
                echo "Deploying to production server AWS"
            }
        }
    }
}
