pipeline {
agent{
label{
		label "built-in"
		customWorkspace "/mnt/master"
        }
    }
    stages {

       stage ("on master") {
			steps {
					sh "git clone https://github.com/Sagar-Nakade/assignment-4.git --branch master"
			}
		
		} 
		
		stage ("on slave") {
		agent {
		node {
				label "QA"
				customWorkspace "/mnt/slave@"
		    }
		
		}
		
		steps {
				sh "git clone https://github.com/Sagar-Nakade/assignment-4.git --branch dev"
		
		}
		
    }
    	stage ("on slave-2") {
		agent {
		node {
				label "AQ"
				customWorkspace "/mnt/slave@"
		    }
		
		}
		
	     steps {
				sh "git clone https://github.com/Sagar-Nakade/assignment-4.git --branch qa"
		    }
    	}
	}
}
