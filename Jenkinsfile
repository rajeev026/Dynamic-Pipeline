pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Application Build Started"
            }
        }

        stage('Test') {
            steps {
                echo "Running Tests"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment Successful"
            }
        }
    }

    post {

        success {

            emailext(
                subject: "SUCCESS: ${env.JOB_NAME} Build #${env.BUILD_NUMBER}",
                body: """
Build Completed Successfully

Job Name : ${env.JOB_NAME}
Build No : ${env.BUILD_NUMBER}

Build URL:
${env.BUILD_URL}
""",
                to: "rajeev@example.com"
            )
        }

        failure {

            emailext(
                subject: "FAILED: ${env.JOB_NAME} Build #${env.BUILD_NUMBER}",
                body: """
Build Failed

Job Name : ${env.JOB_NAME}
Build No : ${env.BUILD_NUMBER}

Build URL:
${env.BUILD_URL}
""",
                to: "rajeev@example.com"
            )
        }
    }
}
