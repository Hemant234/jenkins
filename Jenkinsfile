node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	
	shortCommit = bat(returnStdout: true, script: 'git log --pretty=format:"%h %an %ar %s"')
	println shortCommit
	}
}
