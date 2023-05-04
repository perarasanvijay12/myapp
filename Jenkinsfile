pipeline{
    
    agent any

    stages{

        stage('Git checkout'){

            steps{

                script{

                    git branch: 'main', credentialsId: '7754e6b8-7ec9-474d-8fa6-6fb6dc00eb4b', url: 'https://github.com/perarasanvijay12/myapp.git'
                }
            }

        }
    }
}