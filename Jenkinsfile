pipeline {
    agent any
	

 stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/srikanta1219/devops-practical-2.git'
             
          }
        }
       

  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t babaijenkinstest:latest .' 
               
                sh 'docker tag babaijenkinstest bibhu1234567890/babaijenkinstest:$BUILD_NUMBER'
               
          }
        }
  stage('Publish image to Docker Hub') {
            steps {
        withDockerRegistry([ credentialsId: "DockerHub", url: "" ]) {
           sh  'docker push bibhu1234567890/babaijenkinstest:$BUILD_NUMBER'
	   sh  'pwd'	
		}
                  
          }
        }
		
    }
}
