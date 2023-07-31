pipeline {
       agent {
	     label { 
		  label "master"
		      }
	         }
	       stages {
		     stage ("clean workspace") {
			 steps {
				cleanWsp()
			 }
			 }
		    stage ("clone ropo") {
		     steps {
			  sh "git clone https://github.com/adinathshelke/webapp.git"
		       }
		 }
	   }
}

