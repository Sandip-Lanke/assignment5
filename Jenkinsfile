
pipeline {
      agent{
	      label{
		        label'built-in'
				customWorkspace'/mnt/assignmet4/22Q1'
		  } 
	  }
	  stages{
	  
	          stage('docker-volume-22Q1'){
		           steps {
				        sh "docker volume create vol-22Q1"
					    sh "cd /mnt/assignmet4/22Q1 && cp index.html /var/lib/docker/volumes/vol-22Q1/_data"
							
				        }
		    }
		   
	           /* stage('stage1-22Q1'){
			     steps {
				       sh "docker kill 22Q1-httpd"
				       sh "docker rm 22Q1-httpd"
				       
				   }
			   } */
			stage('docker-stage-22Q1'){
			      steps{
				       sh "chmod -R 777 /mnt/assignmet4/22Q1/index.html" 
						sh "docker run --name 22Q1-httpd -itdp 80:80 -v vol-22Q1:/usr/local/apache2/htdocs httpd"           
						
				  }
			}
	  }
	  
}



