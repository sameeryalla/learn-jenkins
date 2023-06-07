pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    triggers {
        pollSCM ('H/2 * * * *')
        }
    options {
        ansiColor('xterm')
    }
    parameters {
        string(name:'PERSON', defaultValue:'Mr Jenkins', description: 'Who should I say hello')
    }
    environment {
        sample_url="www.example.com"
    }
    stages {
        input {
           message "Should we continue?"
           ok "Yes, we should."
           submitter "alice,bob"
           parameters {
                            string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
           }
        }
        stage ('One') {
            input {
                message "Do you approve?"
                ok "Yes"
            }
            steps {
                sh 'echo world 1'
                sh 'echo ${sample_url}'
            }

        }
        stage ('Two') {
            steps {
                sh 'echo world 2'
                sh 'echo world 3'
            }
        }
    }
    post {
        always {
            sh 'echo post run with always block'
        }
    }
}