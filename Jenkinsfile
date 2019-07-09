pipeline{
    agent any
	tools {
	jdk "jdk_8"
	ant "Ant-1.9"
	}
	
	stages{
	
	  stage('Clone sources'){
	  
	  steps{
	       git url: 'https://github.com/anu0393/Ant.git'
		   }
		   }
		   
		   stage("Build") {
            steps {
                echo "Building application..."   
                bat(script: 'build.xml', returnStatus: true)
            }
        }
		
		stage("Deploy") {
            steps {
		    echo "Deploying to tomcat 7.x"
		 bat 'cp **/*.war http://localhost:8080'
            }
        }
	}
}
