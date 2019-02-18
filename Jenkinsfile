node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	shorttime= bat(returnStdout: true, script: "prompt $t$g")
	dir ('$shorttime') {
        writeFile file:'dummy', text:''
	
	shortCommit = bat(returnStdout: true, script: "git log -1")
	writeFile file: "Commitversion.txt", text: "$shortCommit"
	}
	
	}
}
