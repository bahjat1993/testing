pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                set
                script {
                version_stuff = readFile('output.txt').trim()
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
