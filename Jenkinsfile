pipeline  {
   agent { label 'JDK17' }
   stages  {
          stage ('SourceCode')  {
             steps {
                   git branch: 'mybranch', url: 'https://github.com/teji145/spring-petclinic.git'
              }
           }
             stage('build the code')  {
             steps   {
               sh 'mvn clean package'
    }
  }
             stages ('Archiving and test Results')   {
                steps  {
         junit '**/surefire-reports/*.xml'
         archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
      }
    }
   }
  }
