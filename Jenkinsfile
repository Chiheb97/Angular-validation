pipeline {
	    agent any
	    tools {nodejs "nodejs"}
	    stages {
	        stage ('GIT pull angular') {
            steps {
               echo "Getting Project from Git";
                git branch: "main",
                    url: "https://github.com/Chiheb97/Angular-validation"
            }
        }
	        }
	        
	             	
	        stage('npm install'){
	            steps{
	                script{
	                    sh "npm install "
	                }
	            }
	        }
		    
		stage('python test'){
	            steps{
	                script{
	                    sh "python3 --version"
	                }
	            }
	        }
		    
	        stage('Build'){
	            steps{
	                script{ 
	                    sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
	                }
	            }
	            }
	              stage('docker'){
            steps{
                script{
                    sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml"
                }
            }
        }
       


 }
	            
