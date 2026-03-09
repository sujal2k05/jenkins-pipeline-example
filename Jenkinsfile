pipeline {
    agent any

    tools {
        maven "MAVEN"
        jdk "JDK"
    }

    stages {

        stage('Initialize') {
            steps {
                echo "Pipeline Started"
            }
        }

        stage('Build') {
            steps {
                bat "mvn -B -DskipTests clean package"
            }
        }

    }

    post {
        always {
            junit allowEmptyResults: true, testResults: '**/test-reports/*.xml'
        }
    }
}
