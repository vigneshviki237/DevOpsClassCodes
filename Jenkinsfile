pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Git checkout from the specified URL and branch
                git branch: "${params.branches}", credentialsId: '', url: 'https://github.com/vigneshviki237/DevOpsClassCodes.git'
            }
        }
        stage('Package or compile') {
            steps {
                script {
                    if (params.branches == 'main') {
                    withMaven(maven : 'Maven') {
                    sh 'mvn package'
                    }
                    else {
                        withMaven(maven : 'Maven) {
                    sh 'mvn compile'
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
