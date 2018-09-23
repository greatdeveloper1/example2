pipeline{

	agent any

	parameters{
	
	string(name: 'dockerPath', defaultValue: '"C:\\Program Files\\Docker Toolbox\\"', description: '')

	}	
	
	environment {
    PATH = "${dockerPath}:${env.PATH}"
    }
	stages{
	
		stage('me Building docker image'){
			
			steps{
			
				echo env
				echo 'clean and package....'
				bat 'mvn clean package'
				bat " docker build -t tomcatwebapp:${env.BUILD_ID} ."
			
			}
			post{
			
				success{
					
					echo 'gooooooooooood'
					
				}
			
			}
		
		}
	
	}
}
