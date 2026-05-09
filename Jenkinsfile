pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Build and package the Node.js application.'
                echo 'Tool: npm'
                bat 'npm install'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Run unit and integration tests to check application functionality.'
                echo 'Tool: npm test / Mocha'
                bat 'npm test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Analyse source code quality and coding standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scan project dependencies for security vulnerabilities.'
                echo 'Tool: npm audit / Snyk'
                bat 'npm audit'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Task: Deploy application to staging server.'
                echo 'Tool: AWS EC2'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Task: Run integration tests in staging environment.'
                echo 'Tool: Postman/Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Task: Deploy application to production server.'
                echo 'Tool: AWS EC2'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}