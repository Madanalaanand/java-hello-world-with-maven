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
     withSonarQubeEnv('SONAR_9.2.3') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
       sh '/usr/local/apache-maven-3.8.4/bin/mvn sonar:sonar -Dsonar.login=f10e88b69e2251c730bec38903e2d8ad5eec4956'

   }
  }
}