pipeline{
	agent none
	stages{
		stage("Non parallel stage"){
			
			agent {
				
				label "master"
			}
			
			steps{
				echo "This step will execute first"; 
			}
		}
		
		stage('Run Tests'){
			
			parallel {
				stage("Test on Windows_Node"){
					
					agent {
					
						label "Windows_Node"
					}
					
					steps{
						
						echo "Task 1 on Agent"
					}
					
				}
				
				stage("Test on master"){
					
					agent {
					
						label "master"
					}
					
					steps{
						
						echo "Task 1 on master"
					}
					
				}
			
			}
		}
		
	}
}
