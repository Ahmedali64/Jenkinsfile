pipeline{
    agent any 
    environment {
    Build_Message = 'Hello From jenkins Env Var'
    }

   parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to build') // String parameter for branch name

        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy the application?') // Boolean parameter for deployment
    }

    stages {

        stage("Build"){
            steps{
                echo 'Message: ${env.Build_Message}'
                echo "Building branch${params.BRANCH}" 
            }
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
        
        stage("Deploy"){
            when{ expression {params.DEPLOY} }
            steps{ echo "Deploying ...."}    
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


