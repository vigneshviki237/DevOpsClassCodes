pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Git checkout from the specified URL and branch
                git branch: "${params.branches}", credentialsId: '', url: 'https://github.com/vigneshviki237/DevOpsClassCodes.git'
            }
        }
        stage('Maven Compile and Test') {
            steps {
                script {
                    if (params.branches == 'test') {
                            echo "test branch"
                    }
                    else {
                        echo " this is not test branch, DEVELOPPPP"
                    }

                }
            }
        }
    }

    post {
        always {
            echo 'This step always runs after the pipeline'
        }
        success {
            echo 'This step runs only if the pipeline succeeds'
        }
        failure {
            echo 'This step runs only if the pipeline fails'
        }
    }
}
