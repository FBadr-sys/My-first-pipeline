pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
    }
    environment {
     MAVEN_OPTS: "-Dmaven.repo.local=$CI_PROJECT_DIR/.m2/repository"
     MYSQL_DATABASE: $MYSQL_TEST_DB
     MYSQL_ROOT_PASSWORD: $MYSQL_ROOT_PWD
     MYSQL_USER: $MYSQL_USER
     MYSQL_PASSWORD: $MYSQL_USER_PWD
    }
    
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