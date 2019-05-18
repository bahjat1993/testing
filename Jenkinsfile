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
                               script {
                    def bRun = build 'anotherJob' 
                    echo 'last 100 lines of BuildB'
                    for(String line : bRun.getRawBuild().getLog(100)){
                        echo line
                    }
                 

               
                
            }
        }
    }
	}
    post{
        always{
            echo "${version_stuff}"
            mail to: "${version_stuff}", subject: 'New build is waiting for your decision', body: 'Please make your decision about new build in Jenkins!'
        }
    }

}
