pipeline {
    agent any

    environment {
        TAG_NAME = "v1.${env.BUILD_ID}" // Replace with your desired tag name
    }

    stages {
        stage('git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aa30sharma/test.git'
                }
            }
        }
        stage('Push Tag') {
            steps {
                script {
                        sh "git tag ${TAG_NAME} "
                        sh "git push origin ${TAG_NAME} "
                }
            }
        }
    }
}
