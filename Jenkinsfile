pipeline {
    agent any
    stages {
        stage('build') {
            steps {
           sh 'mvn -B -DSkiptests clean install'
            }
        }
         stage('Test') {
            steps {
            sh 'mvn test'
            }
         post {
			    always {
			        junit 'target/surefire-reports/*.xml'
			    }
         }
        }
        stage('delivery') {
			steps {
			           sh './scripts/deliver.sh'
        }   
    }
  }
}
