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
        

        stage('Deploy Based on ENV_TYPE') {
            steps {
                script {
                    if (params.ENV_TYPE == 'A') {
                        MY_VARIABLE = "subnet-ab9019anbdhda"
                    } else if (params.ENV_TYPE == 'B') {
                        MY_VARIABLE = "subnet-ab9019anbdhdb"
                    } else if (params.ENV_TYPE == 'C') {
                        MY_VARIABLE = "subnet-ab9019anbdhdc"
                    } else {
                        echo "Unknown environment!"
                    }
                }
            }
        }
    
	stage('Do something fun') {
            steps {
                script{
                        sh "chmod +x ./fun.sh"
                        sh "./fun.sh $MY_VARIABLE"
 
            }
        }

    }
  }
}
