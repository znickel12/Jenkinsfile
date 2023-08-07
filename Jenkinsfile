pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/rebeccanickel/.jenkins"
        TESTING_ENVIRONMENT= "SANDBOX"
        PRODUCTION_ENVIRONMENT= "Zachary Nickel"
    }
    stages{
        stage('Build'){
            steps{
                echo "fetch the source code from the directory path: $DIRECTORY_PATH"
                echo "Compile the code and generate any necessary artefacts"
            }
        }    
        stage('Unit and Integration Tests'){
            steps{
                echo "Units Tests"
                echo "Integration Tests"
            }
            post{
                success{
                    mail to: "zacandbel@gmail.com",
                    subject: "Testing Status",
                    body: "Testing completed successfully"
                }
            }
        }    
        stage('Code Analysis'){
            steps{
                echo "Check the quality of the code"
            }
        }    
        stage('Security Scan'){
            steps{
                echo "Scan for vulnerabilities"
            }
            post{
                success{
                    mail to: "zacandbel@gmail.com",
                    subject: "Security Scan Status",
                    body: "Scanning completed successfully"
                }
            }
        }    
        stage('Deploy to Staging'){
            steps{
                echo "Deploy the application to a testing environmebnt: $TESTING_ENVIRONMENT"
            }
        }    
        stage('Integration Tests on Staging'){
            steps{
                sleep(time: 10)
            }
        }    
        stage('Deploy to Production'){
            steps{
                echo "Deploy code to the production environment: $PRODUCTION_ENVIRONMENT"
            }
        }    
    }
}