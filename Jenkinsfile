pipeline{
    agent any
    stages{
        stage('Stage 1'){

            steps {
		    
		    
            
		    
		    
		    
                echo 'hello world'
				bat label: '', script: 'cd'
				echo "${BUILD_NUMBER}"
				script
				{
				number="${BUILD_NUMBER}"
				}
				
				bat label: '', script: 'cd builds\${number}'
				bat label: '', script: 'cd'

				

				


			
				
                bat label: '', script: 'python python_test.py'
                script {
                version_stuff = readFile('output.txt').trim()
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
			script {
                version_stuff = readFile('buildlog.txt').trim()
					}
			}
	}
    }	
	

    post{
        always{
		echo "printing out what is stored in version_stuff now"
		echo "${version_stuff}"
		echo "finished printing"
		mail to: "khanbahjat@Hotmail.com", subject: 'New build is waiting for your decision', body: "${version_stuff}"

        }
    }
}
