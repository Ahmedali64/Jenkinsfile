pipeline{
    agent any 

   parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to build') // String parameter for branch name

        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy the application?') // Boolean parameter for deployment
    }

    stages {

        stage("Build"){
            steps{echo "Building branch${params.BRANCH}" }
        }

        stage("Deploy"){
            when{ expression {params.DEPLOY} }
            steps{ echo "Deploying ...."}    
        }

        stage('Parallel Stage') {
            parallel {
                stage('Test 1') {
                    steps {
                        echo 'Running Test 1...'
                    }
                }
                stage('Test 2') {
                    steps {
                        echo 'Running Test 2...'
                    }
                }
            } 
        }
    }
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            echo 'This will always run.'
        }
    }
}


