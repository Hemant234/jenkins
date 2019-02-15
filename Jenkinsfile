node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	
	shortCommit = bat(returnStdout: true, script: "git log ")
	print(shortCommit)
	}
}
