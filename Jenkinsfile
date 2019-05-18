pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                script {
                version_stuff = readFile('output.txt').trim()
                }
            }
        }
    }
	stage('save log build') {
    steps {
        script {
            def logContent = Jenkins.getInstance()
                .getItemByFullName(env.JOB_NAME)
                .getBuildByNumber(
                    Integer.parseInt(env.BUILD_NUMBER))
                .logFile.text
            // copy the log in the job's own workspace
            writeFile file: "buildlog.txt", text: logContent
				}
			}
	}
	
	

    post{
        always{
		echo "${version_stuff}"
//		mail to: "${version_stuff}", subject: 'New build is waiting for your decision', body: "Stuff"

        }
    }
}
