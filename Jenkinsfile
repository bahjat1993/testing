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
		
		script{
            env.ForEmailPlugin = env.WORKSPACE      
            emailext attachmentsPattern: 'TestResults\\*.trx',      
            body: '''${SCRIPT}''', 
            subject: currentBuild.currentResult + " : " + env.JOB_NAME, 
            to: 'khanbahjat@Hotmail.com'
		}

        }
    }

}
