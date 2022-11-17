pipeline {
	    agent any
       tools {nodejs "node"}
	    stages {
	        stage ('GIT pull angular') {
            steps {
               echo "Getting Project from Git";
                git branch: "main",
                    url: "https://github.com/Chiheb97/Angular-validation"
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
	                    sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
	                }
	            }
	            }
	              stage('docker'){
            steps{
                script{
                    sh "ls"
                }
            }
        }
       stage('docker-registry'){
            steps{
                script{
                    sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml"
                }
            }
        }
      stage('run prometheus and grafana containers'){
            steps{
                script{
                    sh "docker restart grafan && docker restart prom"
                }
            }
        }


 }}

