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
                sh 'if [ -d EC2 ]; then  rm -rf EC2; fi'
            }
        }
        
        stage('git clone') {
            steps {
                sh 'git clone https://github.com/santhosh1994m/EC2.git'
            }
        }
        
         stage('sleep') {
            steps {
                sh 'sleep 10'
            }
        }
        
        stage('terraform init') {
            steps {
             
               sh 'sudo /usr/local/bin/terraform init ./EC2'
       
            }
        }
       // stage('terraform workspace new') {
        //    steps {
           
         //      sh 'sudo /usr/local/bin/terraform workspace new QA ./EC2'
          
        //    }
      //  }
        
       stage('terraform workspace select') {
           steps {
               {
               sh 'sudo /usr/local/bin/terraform workspace select QA ./EC2'
               }
            }
       }
        
        
        stage('terraform plan') {
            steps {
          
               sh 'sudo /usr/local/bin/terraform plan ./EC2'
         
            }
        }
      //  stage('terraform apply'){
      //      steps{
     //          sh 'sudo /usr/local/bin/terraform apply -auto-approve ./EC2'
       //     }
      //  }
       stage('terraform destroy'){
           steps{
               sh 'sudo /usr/local/bin/terraform destroy -auto-approve ./EC2'
            }
        }
        
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }


        
    }
}
