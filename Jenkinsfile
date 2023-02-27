node {
    stage ("Checkout ClientService"){
        git branch: 'master', url: 'https://github.com/imcbee/Team1-JavaJive-Auth-Frontend.git'
    }
    
    stage ("NPM Build - ClientService") {
	
		sh 'pwd'
		sh 'npm install'
		sh 'npm audit fix --force'
    }
    
    // stage ("NPM Start - ClientService") {
    //		sh 'pwd'
    //		sh 'npm start'
    // }
    
}

