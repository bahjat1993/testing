pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
    finally {
        println currentBuild.result  // this prints null
        step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'khanbahjat@hotmail.com', sendToIndividuals: true])
    }
 

            }
        }
    }
}
