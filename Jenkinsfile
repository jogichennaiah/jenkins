pipeline {
    agent any
    environment {
        ENV_URL  = "pipeline.google.com"
        SSH_CRED = credentials('SSH_CRED')

    }

    triggers {
         pollSCM('* * * * *')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Stage One') {
            environment {
                 ENV_URL = "stage.google.com"
            }
            steps {
               sh '''
               echo Hello World
               echo Welcome To  Jenkins
               echo Environment URL is ${ENV_URL}
               env
               maven clean
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


