node('jdk11-mvn3.8.4') {
  properties([pipelineTriggers([cron('* */3 * * 0,6')])])
  properties([pipelineTriggers([pollSCM('*/5 * * * *')])])
  stage('git') {
      git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
  }
  stage('build') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
  }
  stage('build') {
       junit '**/TEST-*.xml'
  }
}