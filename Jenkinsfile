node('JDK17')  {
   stage('sourcecode')  {
  //get the code from git repo
 git branch: 'mybranch', url: 'https://github.com/teji145/spring-petclinic.git'
  }
  stage ('build the code')  {
   //build the code from mvn
  sh 'mvn clean package'

}
    stage ('Archive the Test Results')  {
   //archive and test the code
   junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
   archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
   }
 }
