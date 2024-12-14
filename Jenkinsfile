node('JDK17') {
        stage('sourceCode') {
                   //get the code from git repo   
                   git branch: 'mybranch', url: 'https://github.com/teji145/spring-petclinic.git'
       }
        stage('Build the code')  {
                 sh '/opt/apache-maven-3.9.9/bin/mvn'
        }
     
        stage('Archiving and Test Results')  {
          junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
          archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
    }
}
 

