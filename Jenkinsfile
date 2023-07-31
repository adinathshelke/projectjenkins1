pipeline {
       agent {
	     label { 
		  label "master"
		    customWorkspace "/mnt/adinath"
		      }
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
	   }
}
