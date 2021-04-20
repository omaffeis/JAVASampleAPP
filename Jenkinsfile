pipeline{
    agent{
        label "master"
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                echo "========Build Maven========"
                sh mvn clean install
                '''
            }
        }
    }
}