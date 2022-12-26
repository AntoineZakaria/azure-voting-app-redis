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
		"""

            }
        }
	stage('Push Container') {
            steps {
		echo "workspace is $WORKSPACE"
		dir("$WORKSPACE/azure-vote"){
			script{
				docker.withRegistry('https://index.docker.io/v1','Docker'){
					def image = docker.build('blackdentech/jenkins-course:latest')
					image.push()
				}
			}

		}
                 

            }
        }
    }
}
