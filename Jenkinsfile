pipeline {
    agent any // This means the pipeline can run on any available Jenkins agent

    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to build') // String parameter for branch name
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy the application?') // Boolean parameter for deployment
    }

    stages {
        stage('Build') {
            steps {
                echo "Building branch: ${params.BRANCH}" // Print the branch name chosen
            }
        }

        stage('Deploy') {
            when {
                expression { params.DEPLOY } // This stage only runs if DEPLOY is true
            }
            steps {
                echo 'Deploying...' // Print that the deployment is happening
            }
        }
    }
}
