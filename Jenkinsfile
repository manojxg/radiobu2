pipeline {
    agent any

    parameters {
        choice(
            name: 'ENV_TYPE',
            choices: ['A', 'B', 'C'],
            description: 'Select environment type'
        )
    }

    stages {
        stage('Print Environment') {
            steps {
                script {
                    // Calling ENV_TYPE parameter
                    def env = params.ENV_TYPE
                  //  echo "You selected environment: $env"
                }
            }
        }
        stage('Do something fun') {
            steps {
                script{
			// subnetazA = params['ENV_TYPE']
                        sh "chmod +x ./fun.sh"
                        sh "./fun.sh ${ENV_TYPE}"
 
            }
        }

    }

        stage('Deploy Based on ENV_TYPE') {
            steps {
                script {
                    if (params.ENV_TYPE == 'A') {
                        echo "subnet-ab9019anbdhda"
                    } else if (params.ENV_TYPE == 'B') {
                        echo "subnet-ab9019anbdhdb"
                    } else if (params.ENV_TYPE == 'C') {
                        echo "subnet-ab9019anbdhdc"
                    } else {
                        echo "Unknown environment!"
                    }
                }
            }
        }
    }
}
