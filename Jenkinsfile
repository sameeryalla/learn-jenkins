pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    stages {
        stage ('stage1') {
            steps{
                sh 'echo hello world1'
            }
        }
        stage ('stage2') {
            steps {
                sh 'echo hello world2'
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