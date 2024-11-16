pipeline{
    environment{
        node_Version = '18.x'
    }
    tools{
        nodejs "${node_Version}"
    }
    stages{
        steps('Checkout'){
            checkout scm
        }
        stage("install dependencies"){
            steps{
                script{
                    if(isUnix()){
                        sh 'npm install'
                    }
                    else{
                        sh 'npm install'
                    }
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