pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    stages {
        stage ('one') {
            steps {
                sh 'echo world 1'
            }

        }
        stage ('two') {
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