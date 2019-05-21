pipeline{
    agent any
    stages
	{
        stage('Stage 1')
		{
            steps {
                echo 'hello world'

					
			}
        }
    }	
	

    post
	{
        always
		{
		echo "printing out what is stored in version_stuff now"
		echo "${version_stuff}"
		echo "finished printing"
		mail to: "khanbahjat@Hotmail.com", subject: 'New build is waiting for your decision', body: "${version_stuff}"

        }
    }
}
