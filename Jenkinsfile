pipeline {
    agent any 
    stages {
        stage('packageging') {
            steps {
                echo "Hello Stage 1"
            }
        }
        stage('integrationtest') {
            steps {
                echo "Hello Stage 2"
            }
        }
        stage('build_docker_image') {
            steps {
                echo "Hello Stage 3"
            }
        }
        stage('run_container') {
            steps {
                echo "Hello Stage 4"
            }
            post {
                always {
                    echo "Hello Stage 5"
                }
            }
        }
    }
}
