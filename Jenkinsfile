pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                //sh "mvn clean"
                withMaven(
                 // Maven installation declared in the Jenkins "Global Tool Configuration"
                maven: 'maven-3.6', mavenSettingsConfig: 'my-maven-settings') {
                // Run the maven build
                sh "mvn clean verify"
                  } 
            }
        }
        stage('--test--') {
            steps {
                withMaven(maven: 'maven-3.6'){
                sh "mvn test"
                }
            }
        }
        stage('--package--') {
            steps {
                withMaven(maven: 'maven-3.6'){
                sh "mvn package"
                }
            }
        }
    }
}
