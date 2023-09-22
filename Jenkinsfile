pipeline {
    agent {
      label 'workstation'
    }
    environment {
        ENV_URL  = "pipeline.google.com"
        SSH_CRED = credentials('SSH_CRED')

    }

    triggers {
         cron('57 12 * * *')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    tools {
        maven 'maven-3.8.6' 
    }
    stages {
        stage('Parallel Demo') {
            parallel{ 
                stage('Stage One') {
                   environment {
                      ENV_URL = "stage.google.com"
            }
            steps {
                      sh '''
                      echo Hello World
                      echo Welcome To  Jenkins
                      echo Environment URL is ${ENV_URL}
                      mvn -v
                      hostname
                      sleep 10
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
                sh "sleep 30"
            }
        }
        stage('Stage Three') {
            steps {
                sh "echo Stage Three demo "
                sh "sleep 50"
                  }

               }

            }
        }
    }
}


