pipeline {
    parameters {
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
}
    agent any 
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
     stage('Test') {
    when {
        expression { return params.executeTests }
    }
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
