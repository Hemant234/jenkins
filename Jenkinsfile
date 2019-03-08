node('') {
	
 	stage('checkout'){      
    	   git(
       url: 'https://github.com/Hemant234/jenkins.git',
       credentialsId: '	d5810384-46fe-4a24-a05b-0f7eefcea946',
       branch: "master"
    )
	}
	stage('setup'){
	powershell 'pwd'
	//shorttime= bat(returnStdout: true, script: "prompt $t$g")
	def date = new Date()
	date=date.format("yyMMdd.HHmm", TimeZone.getTimeZone('IST'))
	println date
	workspace_env= env.WORKSPACE
	dir ("$date") 
	{
	shortCommit = bat(returnStdout: true, script: "git log -1")
	writeFile file: "Commitversion.txt", text: "$shortCommit"
	bat 'xcopy "C:/Program Files (x86)/Jenkins/workspace/Build_machine pull"'
	}
	dir("$workspace_env"){
	bat ''' FOR /f "tokens=*" %%a in ('dir *@tmp /A:D /B') DO RMDIR /S /Q %%a''' 
	}
  }
	
notifyBuild('SUCCESSFUL')
}
	def notifyBuild(String buildStatus = 'STARTED') {
  // build status of null means successful
  buildStatus =  buildStatus ?: 'SUCCESSFUL'

  // Default values
  def colorName = 'RED'
  def colorCode = '#FF0000'
  def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
  def summary = "${subject} (${env.BUILD_URL})"

  // Override default values based on build status
  if (buildStatus == 'STARTED') {
    color = 'YELLOW'
    colorCode = '#FFFF00'
  } else if (buildStatus == 'SUCCESSFUL') {
    color = 'GREEN'
    colorCode = '#00FF00'
  } else {
    color = 'RED'
    colorCode = '#FF0000'
  }

  // Send notifications
  slackSend (color: colorCode, message: summary)
	}
}
}
