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
		
		        stage('Email')
        {
            env.ForEmailPlugin = env.WORKSPACE      
            emailext attachmentsPattern: 'TestResults\\*.trx',      
            body: '''${SCRIPT, template="groovy_html.template"}''', 
            subject: currentBuild.currentResult + " : " + env.JOB_NAME, 
            to: 'khanbahjat@Hotmail.com'
        }

        }
    }

}
