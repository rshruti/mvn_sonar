pipeline{
    agent any
    stages{
        stage('SCM-Checkout'){
            steps{
        git 'https://github.com/rshruti/mvn_sonar.git'
            }
        }
         stage('Build'){
            steps{
                echo "Build successful"               
            }
        }  
        stage('junit test'){
            steps{
          echo "junit test is successful"
            }
        }
        stage('Deploy'){
            steps{
          echo "Deployment is successful"
            }
        }
        
            }
        }
