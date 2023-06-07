pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    triggers { pollSCM('H/1 * * * * ')}
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
        stage ('One') {
            steps {
                sh 'echo world 1'
                sh 'echo ${sample_url}'
            }

        }
        stage ('Two') {
            steps {
                sh 'echo world 2'
            }
        }
    }
    post {
        always {
            sh 'echo post run with always'
        }
    }
}