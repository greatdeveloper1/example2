pipeline{

	agent any

	parameters{
	
	string(name: 'dockerPath', defaultValue: '"C:\\Program Files\\Docker Toolbox\\docker-machine.exe"', description: '')

	}	
	
	environment {
    PATH = "${dockerPath}:${env.PATH}"
    }
	stages{
	
		stage('me Building docker image'){
			
			steps{
				echo PATH
				echo 'clean and package....'
				bat 'mvn clean package'
				bat " tcp://192.168.99.100:2376 docker build -t tomcatwebapp:${env.BUILD_ID} ."
			
			}
			post{
			
				success{
					
					echo 'gooooooooooood'
					
				}
			
			}
		
		}
	
	}
}
