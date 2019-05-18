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

    post{
        always{
		echo "${version_stuff}"
		script {	
		emailext body: '''${SCRIPT, template="build-report.groovy"}''',
		}
		echo "${SCRIPT}"
		
		//mail to: "${version_stuff}", subject: 'New build is waiting for your decision', body: "{$BUILD_LOG}"

        }
    }

}
