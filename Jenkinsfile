pipeline{
    agent {
        label 'Agent-SPC'
    }
    parameters{
        string(
            name:'Git_Branch',
            defaultValue:'develop',
            description:'Switching_gitBranch'
            )
    }
    stages{
        stage('check-out'){
            steps{
                git branch: params.Git_Branch, 
                url: 'https://github.com/PRDevopsProjects/Jenkins_Declarative_SPC.git'
            }
        }
        stage('Build_App'){
            steps{
               sh 'mvn clean package'
            }
        }   
        stage('Git_Branch_info'){
            steps{
                echo "Git_Branch_Name: ${params.Git_Branch}"
            }
        }    
    }
}