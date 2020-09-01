pipeline{
    agent any
    tools {
       maven 'M2_HOME'
    }
    stages {
       
        stage('Build'){
            steps{
                echo "build step"
                sh 'mvn clean'
		sh 'mvn install'
		sh 'mvn package'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
         
            }
        }
        stage('Deploy'){
            steps{
                echo "test step"
                
            }
        }
	stage('Build and Publish image'){
            steps{
              script{
                  checkout scm
                  docker.withRegistry('', 'DockerRegistryID'){
                      def customImage = docker.build("ntbolan88/hols-pipeline:${env.BUILD_ID}")
                      customImageImage.push()
                  }
              }
                
           } 
        }
    }
}
