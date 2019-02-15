node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	
	shortCommit = bat(returnStdout: true, script: "git log -n 1 --pretty=format:'%h - %an, %ar : %s'").trim()
	print(shortCommit)
	}
}
