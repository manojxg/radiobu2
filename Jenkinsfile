pipeline {
    agent any

    parameters {
        choice(
            name: 'ENV_TYPE',
            choices: ['dev', 'stage', 'prod'],
            description: 'Select environment type'
        )
    }

    stages {
        stage('Print Environment') {
            steps {
                script {
                    // Calling ENV_TYPE parameter
                    def env = params.ENV_TYPE
                    echo "You selected environment: $env"
                }
            }
        }

        stage('Deploy Based on ENV_TYPE') {
            steps {
                script {
                    if (params.ENV_TYPE == 'dev') {
                        echo "Running development tasks..."
                    } else if (params.ENV_TYPE == 'stage') {
                        echo "Running staging tasks..."
                    } else if (params.ENV_TYPE == 'prod') {
                        echo "Running production tasks..."
                    } else {
                        echo "Unknown environment!"
                    }
                }
            }
        }
    }
}
