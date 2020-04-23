#!groovy
library identifier: 'jenkinsdemo@master', retriever: modernSCM(
        [$class: 'GitSCMSource',
         remote: 'https://github.com/jaypttn/jenkinsdemo'])
pipeline {
   agent any
    options{
       timestamps()
       ansiColor('xterm')
   }
   stages {
      stage('List All files and dir of current path') {
         steps {
             script{
                    sh ''' ls -l
                    '''
                    myscript.info("Successfully Executed")
                    def ret = sh(script: 'lll', returnStatus: true)
                    myscript.warning(ret)
             }
         }
      }
      stage('Git Commit Id') {
         steps {
              script{
		    def gitId=sh(script:'git rev-parse HEAD', returnStdout: true)
                    myscript.gitCommitId(gitId)
             }
         }
      }
   }
}
