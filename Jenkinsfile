pipeline {
    agent any

    environment {
        TARGET_REPO = 'https://github.com/ashisheeSoft/node-repo-two.git'
        FILE_TO_COPY = 'README.md'  // adjust your file name here
        COMMIT_MSG = '🔁 Copied file from main repo'
    }

    stages {
        stage('Clone Target') {
            steps {
                echo '📥 Cloning target repository...'
                sh 'rm -rf node-repo-two'
                sh 'git clone ${TARGET_REPO}'
            }
        }

        stage('Copy and Push File') {
            steps {
                echo '📤 Copying file and pushing to target repo...'
                // Use Jenkins credentials for Git push
                withCredentials([usernamePassword(credentialsId: 'git-token-admin', usernameVariable: 'GIT_USER', passwordVariable: 'GIT_PASS')]) {
                    sh '''
                        cp ${FILE_TO_COPY} node-repo-two/
                        cd node-repo-two
                        sh "rm -rf ${FILE_TO_COPY}"
                        git config user.email "ashishsharmaen1014@gmail.com"
                        git config user.name "ashisheeSoft"
                        git add ${FILE_TO_COPY}
                        git commit -m "${COMMIT_MSG}" || echo "Nothing to commit"
                        git push https://${GIT_USER}:${GIT_PASS}@github.com/ashisheeSoft/node-repo-two.git HEAD:main
                    '''
                }
            }
        }
    }

    post {
        always {
            echo '✅ Pipeline finished.'
        }
    }
}
