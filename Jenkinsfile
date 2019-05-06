pipeline {
    agent any
    stages {
       stage ('User input') {
            steps {
                script {
                    env.RESP = input id: 'customer-prompt',
                                    message: 'Continue to next stage?',
                                    ok: 'Yes',
                                    submitterParameter: 'approver'
                }
                echo "Answered by ${env.RESP}"
            }
        }
        stage('say Hello') { 
            steps {
                echo "Hello" 
            }
        }
    }
}