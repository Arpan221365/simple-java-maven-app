pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                bat 'C:\\apache-maven-3.8.8\\bin\\mvn -B -DskipTests clean package' 
            }
        }
		stage('Test') {
            steps {
                bat 'C:\\apache-maven-3.8.8\\bin\\mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
		stage('Deliver') { 
            steps {
                bat '''
		    	echo "The following Maven command installs your Maven-built Java application"
			echo "into the local Maven repository, which will ultimately be stored in"
			echo "Jenkins''s local Maven repository (and the "maven-repository" Docker data"
			echo "volume)."
		    '''
            }
        }
    }
}
