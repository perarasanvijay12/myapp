@Library(jenkins_shared_lib) _

pipeline{
    
    agent any

    stages{

        stage('Git checkout'){

            steps{

                script{

                    branch: "main", 
                    url: "https://github.com/perarasanvijay12/myapp.git"
                }
            }

        }
    }
}