pipeline {
       agent {
	     label { 
		  label "master"
		    customWorkspace "/mnt/adinath"
		      }
	         }
	tools {
           maven "3.9.3"
		
	}
	       stages {
		       stage("clean workspace"){
			 steps {
				cleanWs()
			 }
			 }
		     		    stage ("clone repo") {
		     steps {
			  sh "git clone https://github.com/adinathshelke/webapp.git"
		       }
		 }
		     stage ("build") {
			 steps {
				
			   dir ("/mnt/adinath/webapp") {
			    
				sh "mvn clean install"
			 }
			 }
			 
			 }
			 stage ("deploy on jenkins master") {
			 steps {
			  sh "cp -r /mnt/adinath/webapp/target/WebApp.war /mnt/servers/apache-tomcat-9.0.76/webapps/" 
			 }
			 }
			 stage ("deploy on slave1") {
			  steps {
				  sh "scp -i /mnt/keshavnv.pem /mnt/adinath/webapp/target/WebApp.war ec2-user@172.31.85.149:/mnt/servers/apache-tomcat-9.0.76/webapps/"

			  }
			 } 
		        stage ("deploy on slave2") {
			  steps {
				  sh "scp -i /mnt/keshavnv.pem /mnt/adinath/webapp/target/WebApp.war ec2-user@172.31.80.81:/mnt/servers/apache-tomcat-9.0.76/webapps/"

			  }
			 } 
			 
			 
			 
	   }
}
