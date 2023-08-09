pipeline {
    agent any

    environment {
        TAG_NAME = "v1.${env.BUILD_ID}" // Replace with your desired tag name
    }

    stages {

        stage('Push Tag') {
            steps {
                script {
                   withCredentials([usernameColonPassword(credentialsId: 'gitCred', variable: 'GITHUB_TOKEN')]) {
                        sh "git tag ${TAG_NAME} "
                        sh "git push origin ${TAG_NAME}"
                    }
                }
            }
        }
    }
}
