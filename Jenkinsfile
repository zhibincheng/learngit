pipeline {
    agent {
        label 'docker-agent' // 这里使用你刚才设置的 Label
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello, I am running inside a Docker container on a remote machine!"'
                sh 'uname -a'
                sh 'pwd'
            }
        }
    }
}
