@Library('jenkins_shared_lib') _

pipeline{
    
    agent any

    parameters{

        choice(name:'action',choices:'create\ndelete',description:'choose create/destroy')
    }

    stages{

        stage('Git checkout'){
         when{ expression { params.action == 'create'}}

            steps{

                script{

                    gitCheckout(

                        branch: "main", 
                        url: "https://github.com/perarasanvijay12/myapp.git"
                
                    )
                }
            }

        }

        stage('Unit testing maven'){

         when{ expression { params.action == 'create'}}

            steps{

                script{

                    mvntest()

                }
            }

        }

        stage('Integration testing maven'){

         when{ expression { params.action == 'create'}}

            steps{

                script{

                    mvnintegration()
                    
                }
            }

        }

        /*stage('Static code analysis: sonarqube '){

         when{ expression { params.action == 'create'}}

            steps{

                script{

                    def SonarQubecredentialsId = 'sonar-credentials'
                    statiCodeAnalysis(SonarQubecredentialsId)
                    
                    
                }
            }

        }*/

        stage('Quality check: sonarqube '){

         when{ expression { params.action == 'create'}}

            steps{

                script{

                    def SonarQubecredentialsId = 'sonar-credentials'
                    qualitygate(SonarQubecredentialsId)
                    
                    
                }
            }

        }
    }
}