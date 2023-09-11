pipeline{
    agent any
    stages{
        stage("TF Init"){
            steps{
                echo "Executing Terraform Init"
                sh "terraform init -reconfigure"
            }
        }
        stage("TF Validate"){
            steps{
                echo "Validating Terraform Code"
                sh "terraform validate"
            }
        }
        stage("TF Plan"){
            steps{
                echo "Executing Terraform Plan"
                sh "terraform plan"
            }
        }
        stage("TF Apply"){
            steps{
                echo "Executing Terraform Apply"
                sh "terraform apply --auto-approve"
            }
        }
        stage("Invoke Lambda"){
            steps{
                echo "Invoking your AWS Lambda"
             
                sh "aws lambda invoke --function-name yogesh_s_b3_function out --log-type Tail "
                
            }
        }
    }
}
