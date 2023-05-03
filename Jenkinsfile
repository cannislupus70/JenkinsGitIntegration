pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo("Build the code using Maven") 
                //sh 'mvn clean package'
            }   
        }

        stage('Unit and Integration Tests') {
            steps {
                echo("Run unit tests using JUnit, which will ensure code fucnctions as expected") 
               // sh 'mvn test'

                echo("Run integration tests using Selenium")
                //sh 'selenium-runner --config test/config.json'
            }
        }

        stage('Code Analysis') {
            steps {
                echo("Analyze the code using SonarQube")
                //withSonarQubeEnv('SonarQube') {
                  //  sh 'mvn sonar:sonar'
                //}
            }
        }

        stage('Security Scan') {
            steps {
                echo("Perform a security scan using OWASP ZAP")
                //sh 'zap-baseline.py -t http://localhost:8080/myapp -r report.html'
            } 
        }

        stage('Deploy to Staging') {
            steps {
                echo("Deploy the application to a staging server using Docker")
                //sh 'docker build -t myapp .'
                //sh 'docker run -d --name myapp-staging -p 8080:8080 myapp'
            }
            post{
                success {
                    emailext attachLog: true, 
                    body: 'Test was Successful', 
                    replyTo: 'nevilsukhadiya1234@gmail.com', 
                    subject: 'Test status email', 
                    to: 'nevilsukhadiya1234@gmaill.com'
                }
                
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo("Run integration tests on the staging environment using Selenium")
                //sh 'selenium-runner --config test/config-staging.json'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo("Deploy the application to a production server using Docker")
                /*sh 'docker stop myapp-staging'
                sh 'docker rm myapp-staging'
                sh 'docker run -d --name myapp-production -p 80:8080 myapp'*/
            }
        }
    }
}
