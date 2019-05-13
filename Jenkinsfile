pipeline {
    agent any

    stages {
       stage ('User input') {
            steps {
                script {
                    def userInput = input(
                        id: 'userInputs', 
                        message: 'Let\'s promote?', 
                        parameters: [
                            string(
                                defaultValue: 'hello',
                                description: 'hi',
                                name: 'env'
                            ),
                            string(
                                defaultValue: 'jenkins',
                                description: 'hahah',
                                name: 'target'
                            ),
                            choice (
                                name: 'PROFILE',
                                choices: ['dev', 'prod'],
                                description: 'Profile running enviroment project!'
                            ),
                            booleanParam(
                                defaultValue: true,
                                description : "Prerelease setting",
                                name: 'prerelease'
                            ),
                            // [
                            //     $class: 'CredentialsParameterDefinition',
                            //     // credentialType: 'com.cloudbees.jenkins.plugins.sshcredentials.impl.BasicSSHUserPrivateKey',
                            //     credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl',
                            //     defaultValue: '',
                            //     description: 'SSH key for access',
                            //     name: 'SSH',
                            //     required: true
                            // ]
                            file (
                                description: 'Choose file to upload',
                                name: 'local'
                            )
                        ],
                        submitterParameter: 'approver')
                    echo ("Answered by " + userInput['approver'])
                    echo ("PROFILE: " + userInput['PROFILE'])
                    echo ("Env: " + userInput['env'])
                    echo ("Target: " + userInput['target'])
                    echo ("prerelease " + userInput['prerelease'])
                    echo ("UserInput " + userInput)
                }
            }
        }
        stage('Branch Deploy') { 
            steps {
                echo "Hello"
            }
        }
    }
}