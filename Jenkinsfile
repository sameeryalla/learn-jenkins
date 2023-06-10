pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    triggers { pollSCM('H/2 * * * *') }

    options {
        ansiColor('xterm')
    }
    parameters {
        string(name:'PERSON', defaultValue:'Mr Jenkins', description: 'Who should I say hello')
    }
    environment {
        sample_url = 'www.example.com'
    }
    stages {
        stage ('stage1') {
            input {
                message "Do you approve?"
                ok "Yes"
            }
            steps{
                sh 'echo hello world1'
                sh 'echo person - ${PERSON}'
            }
        }
        stage ('stage2') {
            when{
                expression {
                    GIT_BRANCH == 'origin/master'
                }
            }
            steps {
                sh 'echo hello world2'
                sh 'echo ${sample_url}'
            }
        }
    }
    post {
        always {
         sh 'echo clean the build'
         cleanWs()
        }
    }
}