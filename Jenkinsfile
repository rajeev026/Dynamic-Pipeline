pipeline {
    agent any

    parameters {

        choice(
            name: 'TARGET_ENV',
            choices: ['dev', 'staging', 'prod'],
            description: 'Select deployment environment'
        )

        string(
            name: 'APP_VERSION',
            defaultValue: '1.0.0',
            description: 'Application version'
        )

        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run test cases before deployment'
        )
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Version: ${params.APP_VERSION}"
                echo "Target Environment: ${params.TARGET_ENV}"
            }
        }

        stage('Test') {
            when {
                expression { params.RUN_TESTS == true }
            }
            steps {
                echo "Running Test Cases..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Version ${params.APP_VERSION} to ${params.TARGET_ENV}"
            }
        }
    }
}
