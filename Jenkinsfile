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
            stage('Push Tag') {
                steps {
                    script {
                      withCredentials([usernamePassword(credentialsId: 'GITHUB_TOKEN', passwordVariable: 'git_password', usernameVariable: 'git_username')]) {
                        sh "git config --global user.email 'sharmaaatish552@gmail.com'"
                        sh "git config --global user.name 'aa30sharma'"
                        sh "git tag ${TAG_NAME} "
                        sh "git push -u origin ${TAG_NAME} "
                      }
                    }
                }
            }
        }
    }
