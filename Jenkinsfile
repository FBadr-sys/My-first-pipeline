pipeline {
    agent any 
    stages {
        stage('packageging') {
            steps {
                sh 'mvn clean package -P dev'
            }
        }
        stage('integrationtest') {
            steps {
                sh 'mvn clean package -P dev'
            }
        }
        stage('build_docker_image') {
            steps {
                sh 'mvn clean package -P dev'
            }
        }
        stage('run_container') {
            steps {
                sh 'mvn clean verify -P integration-test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}