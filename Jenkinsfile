node {
    
    stage ("Checkout React Client"){
        git branch: 'master', url: 'https://github.com/imcbee/Team1-JavaJive-Auth-Frontend.git'
    }
    
    stage ("Install dependencies - React Client") {
       sh 'npm install'
    }
    
    stage ("Containerize the app-docker build - react client") {
        sh 'docker build --rm -t react:v1.0 .'
    }
    
    stage ("Inspect the docker image - react client"){
        sh "docker images react:v1.0"
        sh "docker inspect react:v1.0"
    }
    
    stage ("Run Docker container instance - react client"){
        sh "docker run -d --rm --name react -p 3000:80 react:v1.0"
    }
	 
	stage('User Acceptance Test - react client') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {
	    stage('Release  - react client') {
	      sh "docker stop react"
	      sh "echo MCC react client service is ready to release!"
	    }
	  }
    }

