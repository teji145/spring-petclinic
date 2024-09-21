pipeline  {
   agent { label 'JDK17' }
   stages  {
          stage('SourceCode')  {
             steps {
                   git branch: 'mybranch', url: 'https://github.com/teji145/spring-petclinic.git'
              }
           }
               stage('Build The Code')  {
               steps {
                     sh 'mvn clean package'
                      }
              }
               stage('Archiving and Test Results')  {
                  steps  {
                         junit '**/surefire-reports/*.xml'
                         archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
              }
           }
       }
  }
