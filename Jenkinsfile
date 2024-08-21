pipeline {
    agent any
    environment {
    	M2_HOME='C:\\apache-maven-3.8.8\\bin\\mvn'
    }
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
		
    }
}
