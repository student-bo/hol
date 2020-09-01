pipeline{
    agent any
    tools {
       maven 'M2_HOME'
    }
    stages {
        stage('Hello'){
            steps{
                echo "Hello World"
         
            }
        }
        stage('Build'){
            steps{
                echo "build step"
                sh 'mvn clean'
		sh 'mvn install'
		sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                echo "deploy step"
         
            }
        }
        stage('Test'){
            steps{
                echo "test step"
                
            }
        }
    }
}
