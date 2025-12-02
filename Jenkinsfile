//hamna alam
//22i-1650
//i am so cool
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat """
                    "${tool('SonarScanner')}\\bin\\sonar-scanner.bat" ^
                      -Dsonar.projectKey=secure-coding ^
                      -Dsonar.sources=. ^
                      -Dsonar.host.url=http://localhost:9000 ^
                      -Dsonar.login=squ_b99c10180e8b525b4cefb7dd7487957a20fe0306
                    """
                }
            }
        }

        stage('Quality Gate') {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }

    }
}
