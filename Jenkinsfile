node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/vlasovasa1975/spring-petclinic.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.
      // mvnHome = tool 'M3'
   }
   stage('Build') {
      // Run the maven build
      //withEnv(["MVN_HOME=$mvnHome"]) {
        // if (isUnix()) {
            sh './mvnw -Dmaven.test.failure.ignore clean package'
       //  } else {
         //   bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
         //}
      // }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
      //emailext body: 'body of email', subject: 'my subject', to: 'erwerw@gmail.com'
   }
}
