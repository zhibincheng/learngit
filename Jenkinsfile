pipeline {
    agent {
        // 这里用Docker Cloud中, 配置好的Agent模版即可
        // image用什么是在这里面配置的
        label 'docker-agent' 
    }
    stages {
        stage('Build') {
            steps {
                sh '~~ echo "Hello, I am running inside a Docker container on a remote machine!"'
                sh 'uname -a'
                sh 'pwd'
            }
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker version'
            }
        }
    }
    // tools {
    //     allure 'allure_2351'
    // }
    // stages {
    //     stage('Setup') {
    //         steps {
    //             sh 'pip install --force-reinstall .'
    //             sh 'nohup python test/utils/mock_server.py &'
    //         }
    //     }
    //     stage('Test') {
    //         steps {
    //             sh 'cd test && python main.py'
    //         }
    //         post {
    //             always {
    //                 allure([
    //                     reportBuildPolicy: 'ALWAYS',
    //                     results: [[path: 'test/cache']]
    //                 ])
    //             }
    //         }
    //     }
    // }
}
