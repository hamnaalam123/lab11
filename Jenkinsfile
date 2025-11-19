pipeline {
    agent any

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    environment {
        VERSION = '1.0'
    }

    tools {
        maven 'MAVEN_HOME'
    }

    stages {

        stage('Build') {
            steps {
                echo "Building version ${VERSION}"
                bat "mvn -version"
            }
        }

        stage('SAST - SonarQube Simulation') {
            steps {
                echo "Running static code analysis (SAST)..."
                echo "Checking code using SonarQube rules..."
                echo "No critical vulnerabilities found."
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests }
            }
            steps {
                echo "Running tests for version ${VERSION}"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${VERSION}"
            }
        }

        stage('Security Gate Simulation') {
            steps {
                echo "Evaluating security quality gate..."
                echo "Security Gate Passed!"
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
