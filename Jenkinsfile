@Library('jenkins_shared_lib') _

pipeline{
    
    agent any

    stages{

        stage('Git checkout'){

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

            steps{

                script{

                    mvntest()

                }
            }

        }

        stage('Integration testing maven'){

            steps{

                script{

                    mvnintegration()
                    
                }
            }

        }
    }
}