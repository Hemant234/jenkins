node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	//shorttime= bat(returnStdout: true, script: "prompt $t$g")
	def date = new Date()
	println date
	dir (date) 
	{
	shortCommit = bat(returnStdout: true, script: "git log -1")
	writeFile file: "Commitversion.txt", text: "$shortCommit"
	}
	
	}
}
