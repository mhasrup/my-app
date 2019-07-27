pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                //sh "mvn clean"
                withMaven(
                 // Maven installation declared in the Jenkins "Global Tool Configuration"
                maven: 'maven-3.6') {
                // Run the maven build
                sh "mvn clean verify"
                  } 
            }
        }
        stage('--test--') {
            steps {
                sh "mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "mvn package"
            }
        }
    }
}
