node() {
	
 	stage('checkout'){
 	checkout scm	
	}
	stage('setup'){
	powershell 'pwd'
	//writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
	shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
	//bat ''' 
	//cd  C:\Build files
	//mkdir 
	//xcopy "C:\Program Files (x86)\Jenkins\workspace\Build_machine pull" "C:\Build files" /s/h/e/k/f/c
	shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h - %an, %ar : %s'").trim()
	print(shortCommit)
	}
}
