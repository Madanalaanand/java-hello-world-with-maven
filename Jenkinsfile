node('jdk11-mvn3.8.4') {
  properties([pipelineTriggers([cron('* */3 * * 0,6')])])
  properties([pipelineTriggers([pollSCM('*/5 * * * *')])])
  properties([parameters([choice(choices: ['main', 'master', 'grill', 'checken'], description: 'second time', name: 'parameters')])])
     stage('git') {
      git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
  }
  stage('build') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
  }
  stage('build') {
       junit '**/TEST-*.xml'
     withSonarQubeEnv(credentialsId: 'SONAR_TOKEN') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
   }
  }
}