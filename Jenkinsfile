pipeline{
    environment{
        node_Version = '18.x'
    }
    tools{
        nodejs "${node_Version}"
    }
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main' , url: 'https://github.com/Toka7a/StudentRegistryAppDemo'
            }
        }
        stage("install dependencies"){
            steps{
                script{
                   
                    bat 'npm install'
                    
                }
            }
        }
        stage("Start application and run tests"){
            steps{
                script{
                    bat 'npm start &'
                    bat 'wait on http://localhost:8090'
                    bat 'npm test'
                }
            }
        }
    }
    post{
        always{
            echo 'CI pipeline completed'
        }
    }
}