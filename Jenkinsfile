pipeline {
    agent any
    triggers {
        // Trigger the pipeline when there's a push to the 'develop' branch
        pollSCM('H/5 * * * *')
    }
    stages {
        stage('Checkout') {
            steps {
                // Pull the latest code from the develop branch
                git branch: 'develop', url: 'git@your-repo-url.git', credentialsId: 'your-credentials-id'
            }
        }
        stage('Pull Git Content to Folder') {
            steps {
                script {
                    // Define the folder where you want to pull the content
                    def folder = 'path/to/your/folder'
                    sh "mkdir -p ${folder} && cp -r . ${folder}"
                }
            }
        }
    }
}
