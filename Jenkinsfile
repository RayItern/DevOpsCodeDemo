pipeline{
            tools{
                jdk 'myjava'
                maven 'mymaven'
            }
            agent any
            stages{
                stage('Checkout'){
                    steps{
                echo 'cloning..'
                        git url: ' https://github.com/RayItern/DevOpsCodeDemo.git'
                    }
                }
                stage('compile'){
                 agent any            
                    steps{
                        echo 'compile the code..'
                        sh 'mvn compile'
                }
             }   
                stage('CodeReview'){
                 agent any           
                    steps{
                    
                echo 'codeReview..'
                        sh 'mvn pmd:pmd'
                    }
                }
                stage('UnitTest'){
                 agent any           
                    steps{
                        sh 'mvn test'
                    }
               }
                   
                stage('Package'){
                  agent any          
        
                    steps{
                        sh 'mvn package'
                    }
                }
            }
        }
