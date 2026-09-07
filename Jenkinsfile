pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package it into a deployable artefact.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to verify individual components behave correctly.'
                echo 'Tool: JUnit'
                echo 'Task: Run integration tests to verify components work together.'
                echo 'Tool: Selenium'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse the source code against industry coding standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan the code and its dependencies for known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the packaged application to the staging server.'
                echo 'Tool: AWS CLI (deploying to an EC2 instance)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests against staging to confirm correct behaviour.'
                echo 'Tool: Postman / Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the validated application to the production server.'
                echo 'Tool: AWS CLI (deploying to an EC2 instance)'
            }
        }
    }
}
