pipeline{

	agent any	
	
	environment {
    PATH = '"C:\\Program Files\\Docker Toolbox":$PATH'
    }
	stages{
	
		stage('me Building docker image'){
			
			steps{
				
				echo 'clean and package....'
				bat 'mvn clean package'
				bat "docker build -t tomcatwebapp:${env.BUILD_ID} ."
			
			}
			post{
			
				success{
					
					echo 'gooooooooooood'
					
				}
			
			}
		
		}
	
	}
}
