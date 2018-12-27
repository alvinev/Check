properties([
    pipelineTriggers([
        [$class: "SCMTrigger", scmpoll_spec: "* * * * *"],
		cron('H/2 * * * *')
    ]),
])

node {
  stage ('Checkout') {
    dir('Repository') {
      git(
      poll: true,
          url: 'https://github.com/alvinev/MyRepository.git',
          credentialsId: 'alvinev',
          branch: 'master'
      )
    }
    dir('Check') {
      git(
      poll: true,
          url: 'https://github.com/alvinev/Check.git',
          credentialsId: 'alvinev',
          branch: 'master'
        )
    }
	
  }
      stage('Test') {
        bat 'echo %CD%'   
    }
 }
