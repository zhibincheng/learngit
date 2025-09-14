pipeline {
    agent {
        docker {
            image 'jenkins/inbound-agent:jdk17'
            args '-v ${WORKSPACE}:/workspace'
        }
    }
    tools {
        allure 'allure_2351'
    }
    stages {
        // stage('Setup') {
        //     steps {
        //         sh 'pip install --force-reinstall .'
        //         sh 'nohup python test/utils/mock_server.py &'
        //     }
        // }
        stage('Test') {
            steps {
                sh 'cd test && python main.py'
            }
            post {
                always {
                    allure([
                        reportBuildPolicy: 'ALWAYS',
                        results: [[path: 'test/cache']]
                    ])
                }
            }
        }
    }
}