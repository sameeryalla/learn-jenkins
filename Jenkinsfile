pipeline {
    agent {
        node {
            label 'workstation'
        }
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