pipline{
    agent any 

   parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to build') // String parameter for branch name

        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy the application?') // Boolean parameter for deployment
    }

    stages {

        stage("Build"){
            steps{echo params.BRANCH}
        }

        stage("Deploy"){
            when{ expression {params.DEPLOY} }
            steps{ echo "Deploying ...."}    
        }
    }
}

    
