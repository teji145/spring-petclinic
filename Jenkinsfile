pipeline  {
       agent {label 'JDK17'}
              options {
           timeout(time: 1, unit: 'HOURS')
              retry(2)
     }
        triggers  {
            cron ('0 * * * *')
    }
     stages  {
          stage ('Source code')  {
             steps {
          git url: 'https://github.com/teji145/spring-petclinic.git',branch: 'mybranch'
     }
   }
          stage ('build the code')  {
                 steps {
             sh script: 'mvn clean package'
        }
     }
         stage('Reporting and Archiving')  {
          steps {
            junit testResults: 'target/surefire-reports/*.xml'
       }
     }
   }
        post {
          success  {
            // send the success email
             echo "success"
     }
          unsuccessful {
            // send the unsuccess email
             echo "failure"
     }
   }
 }

