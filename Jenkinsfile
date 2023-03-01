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
                        git ' https://github.com/RayItern/DevOpsCodeDemo.git'
                    }
                }
                stage('compile'){
                    steps{
                        echo 'compile the code..'
                        sh 'mvn compile'
                }
                }
                stage('CodeReview'){
                    steps{
                    
                echo 'codeReview..'
                        sh 'mvn pmd:pmd'
                    }
                }
                stage('UnitTest'){
                    steps{
                        sh 'mvn test'
                    }
            }
                   
                stage('Package'){
        
                    steps{
                        sh 'mvn package'
                    }
                }
            }
        }
