pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/rebeccanickel/.jenkins"
        TESTING_ENVIRONMENT= "AWS EC2 INSTANCE"
        PRODUCTION_ENVIRONMENT= "AWS EC2 instance: Zachary Nickel"
    }
    stages{
        stage('Build'){
            steps{
                echo "fetch the source code from the directory path: $DIRECTORY_PATH"
                echo "Compile the code and generate any necessary artefacts using MAVEN"
            }
        }    
        stage('Unit and Integration Tests'){
            steps{
                echo "Units Tests"
                echo "Integration Tests"
                echo "Tests performed using automation tool SELENIUM"
            }
            post{
                success{
                    emailext body: "Testing completed successfully",
                    subject: "Testing Status",
                    to: "zacandbel@gmail.com",
                    attachLog: true
                }
            }
        }    
        stage('Code Analysis'){
            steps{
                echo "Check the quality of the code"
                echo "Code quality automation tool used was SONARCLOUD"
            }
        }    
        stage('Security Scan'){
            steps{
                echo "Scan for vulnerabilities using PROBELY"
            }
            post{
                success{
                    emailext body: "Scanning completed successfully",
                    subject: "Security Scan Status",
                    to: "zacandbel@gmail.com",
                    attachLog: true
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
                echo "Integration testing automation performed by SELENIUM"
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