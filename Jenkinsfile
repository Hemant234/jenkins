node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	
	shortCommit = bat(returnStdout: true, script: "git log -1")
	writeFile file: "Commitversion.txt", text: "$shortCommit"
	}
}
