pipeline{
    agent{
        label "master"
    }
    stages{
        stage("Build"){
            steps{
                echo "========Build Maven========"
                mvn clean install
            }
        }
    }
}