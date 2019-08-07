pipeline {
    agent {
        node {
            label 'master'
        }
    }


    stages {


        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        
        stage('chage path') {
            steps {
                sh 'if [ -d DEMO_ECS_S3_Dynamo_Terraform_Code ]; then  rm -rf DEMO_ECS_S3_Dynamo_Terraform_Code; fi'
            }
        }
        
        stage('git clone') {
            steps {
                sh 'git clone https://github.com/santhosh1994m/DEMO_ECS_S3_Dynamo_Terraform_Code.git'
            }
        }
        
         stage('sleep') {
            steps {
                sh 'sleep 10'
            }
        }
        
        stage('terraform init') {
            steps {
               //sh 'cd  /var/lib/jenkins/workspace/'ECS - AWS - TERRAFORM'/DEMO_ECS_S3_Dynamo_Terraform_Code && sudo mkdir .terraform &&  sudo  terraform init '
         //       withAWS(region:'us-west-2',credentials:'AWS_credentials'){
               sh 'sudo /usr/local/bin/terraform init ./DEMO_ECS_S3_Dynamo_Terraform_Code'
         //       }
            }
        }
        stage('terraform plan') {
            steps {
           //     withAWS(region:'us-west-2',credentials:'AWS_credentials'){
               sh 'sudo /usr/local/bin/terraform plan ./DEMO_ECS_S3_Dynamo_Terraform_Code'
           //     }
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }


        
    }
}
