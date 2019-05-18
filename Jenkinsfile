pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
                script {
                version_stuff = readFile ('output.txt')
                }
                 echo "${version_stuff}"

               
                
            }
        }
    }
    post{
        always{
            mail to: ${version_stuff}, subject: 'New build is waiting for your decision', body: 'Please make your decision about new build in Jenkins!'
        
    }

}
