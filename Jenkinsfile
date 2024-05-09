pipeline{
    agent any
    environment{
        EMAIL_ADDRESS = "varunvk4041@gmail.com"
        success_msg = "Stage Successful!"
        failure_msg = "Stage Failed to Execute!"
    }
    stages{
            stage("Build"){
            steps{
                echo "Build the code using 'Gradle' to compile and package the code."
            }
        }
            stage("Unit and Integration Tests"){
                steps{
                    echo "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected using 'Selenium'."
                }
                post{
                    success{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Unit and Integration testing: ${success_msg}",
                            body: "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected using Selenium.",
                            attachLog: true
                        )
                    }
                    failure{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Unit and Integration Testing: ${failure_msg}",
                            body: "THE STAGE COULD NOT BE EXECUTED DUE TO SOME ERROR, SEE LOG FOR ERROR!",
                            attachLog: true
                        )
                    }
                }
            }
            stage("Code Analysis"){
                steps{
                    echo "Integrate 'SolarQube' to analyse the code and ensure it meets industry standards"
                }
            }
            stage("Security Scan"){
                steps{
                    echo "Perform a security scan on the code 'Acunetix' to identify any vulnerabilities."
                }
                post{
                    success{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Security Scan: ${success_msg}",
                            body: "Perform a security scan on the code 'Acunetix' to identify any vulnerabilities.",
                            attachLog: true
                        )
                    }
                    failure{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Security Scan: ${failure_msg}",
                            body: "THE STAGE COULD NOT BE EXECUTED DUE TO SOME ERROR, SEE LOG FOR ERROR!",
                            attachLog: true
                        )
                    }
                }
            }
            stage("Deploy to Staging"){
                steps{
                    echo "Using 'Heroku' to deploy application to staging environment."
                }
            }
            stage("Integration tests on Staging"){
                steps{
                    echo "Using 'GitLab CI/CD to execute integration tests on staging."
                }
                post{
                    success{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Integration tests on Staging: ${success_msg}",
                            body: "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected using Selenium.",
                            attachLog:true
                        )
                    }
                    failure{
                        emailext (
                            to:"${EMAIL_ADDRESS}",
                            subject: "Integration tests on Staging: ${failure_msg}",
                            body: "THE STAGE COULD NOT BE EXECUTED DUE TO SOME ERROR, SEE LOG FOR ERROR!",
                            attachLog: true
                        )
                    }
                }
            }
            stage("Deploy to Production"){
                steps{
                    echo "Using 'Azure DevOps suite' to undergo Continuous Deployment."
                }
            }
        }
}