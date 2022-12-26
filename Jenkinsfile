pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
    }
    stages {
        stage('Docker Build') {
            steps {
                pwsh(script: 'docker images -a')
            }
        }
    }
}
