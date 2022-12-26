pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                pwsh(script: "echo tony")
            }
        }
        stage('Docker Build') {
            steps {
                pwsh(script: 'docker images -a')
		pwsh(script: """
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
