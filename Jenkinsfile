pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                bat 'echo hello'
            }
        }
        stage('Docker Build') {
            steps {
                 bat 'docker images -a'
		 bat """
		   cd azure-vote/
		   docker images -a 
		   docker build -t jenkins-pipeline .
		   docker images -a 
		   cd ..
		""")

            }
        }
    }
}
