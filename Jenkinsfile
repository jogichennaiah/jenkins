pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"

    }

    stages {
        stage('Stage One') {

            steps {
               sh '''
               echo Hello World
               echo Welcome To  Jenkins
               echo Environment URL is ${ENV_URL}
                  '''
            }
        }    
        stage('Stage Two') {
            environment {
                BATCH = "b55"
            }
            steps {
                sh "echo Stage Two demo "
                sh "echo training batch is ${batch}"
            }
        }
        stage('Stage Three') {
            steps {
                sh "echo Stage Three demo "
            }
        }
    }
}


