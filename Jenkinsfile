pipeline{
            tools{
                jdk 'myjava'
                maven 'mymaven'
            }
            agent any
            stages{
                stage('Checkout'){
                    agent any
                    steps{
                echo 'cloning..'
                        git url: 'https://github.com/RayItern/DevOpsCodeDemo.git'
                    }
                }
                stage('Compile'){
                    agent {label 'Agent1'}
                    steps{
                        echo 'compiling...'
                        sh 'mvn compile'
                }
                }
                stage('CodeReview'){
                    agent {label 'Agent1'}
                    steps{
                    
                echo 'codeReview...'
                        sh 'mvn pmd:pmd'
                    }
                }
                stage('UnitTest'){
                    agent {label 'Agent1'}
                    steps{
                    echo 'Testing'
                        sh 'mvn test'
                    }
                    post {
                    success {
                        junit 'target/surefire-reports/*.xml'
                    }
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
