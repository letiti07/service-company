pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/letiti07/service-company.git"
            }
        }
        stage('Build') {
            steps {
                sh "cd service-company/ && mvn package -DskipTests"
            }
        }
        stage('Run') {
            steps {
                sh "cd service-company/ && java -jar target/*.jar"
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
        failure {
            echo 'Build or Run stage failed.'
        }
    }
}
