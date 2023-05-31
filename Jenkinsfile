pipeline{
    agent any
    stages{
        
        stage('Installation'){
            steps{
                sh 'sudo chmod +x googletest/SWEngProject/Linux-CBuild.sh'
                sh 'sudo ./googletest/SWEngProject/Linux-CBuild.sh'
                sh 'ls'
            }
        }
        
        stage('Build'){
            steps{
                sh 'echo "Building..."'
                sh 'chmod +x ./googletest/SWEngProject/Linux-SampleTest.sh'
                sh './googletest/SWEngProject/Linux-SampleTest.sh'
                sh 'ls'
                
        
            }

        }

        stage('Test'){
            steps{
                sh 'echo "Running..."'
                sh './googletest/SWEngProject/ExecSample4'
                sh 'cd googletest/SWEngProject/DockerSwengProject'
                sh 'docker build -t dkr4sweng_test02 .'
                sh 'docker run dkr4sweng_test02'
            }
        }


    }

}
