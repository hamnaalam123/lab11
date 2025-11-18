pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
    when {
        expression { return env.BRANCH_NAME == 'main' }
    }
    steps {
        echo 'Testing only on main branch'
    }
}
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
    always {
        echo 'Pipeline finished.'
    }
}
}
