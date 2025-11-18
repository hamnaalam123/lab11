pipeline {
    agent any 
    environment {
    VERSION = '1.0'
}
    stages {
        stage('Build') {
    steps {
        echo "Building version ${VERSION}"
    }
}
     stage('Test') {
    steps {
        echo "Testing version ${VERSION}"
    }
}
        stage('Deploy') {
    steps {
        echo "Deploying version ${VERSION}"
    }
}
    }
    post {
    always {
        echo 'Pipeline finished.'
    }
}
}
