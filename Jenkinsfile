pipeline{
    agent{
        label "master"
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                echo "========Build Maven========"
                mvn clean install
                '''
            }
        }
    }
}