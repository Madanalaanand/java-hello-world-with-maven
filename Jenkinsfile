node('jdk11-mvn3.8.4') {
  properties([pipelineTriggers([cron('* */3 * * 0,6')])])
  properties([pipelineTriggers([pollSCM('*/5 * * * *')])])
  properties([parameters([choice(choices: ['scripted', 'master', 'jengil'], description: 'fake parameters', name: 'parameters')])])
  stage('git') {
      git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
  }
  stage('build') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
  }
  stage('build') {
       junit '**/TEST-*.xml'
  }
  currentBuild.result = 'SUCCESS'
   catch (err) {
        currentBuild.result = 'FAILURE'
    }
   finally {
        mail to: 'qtdevops@gmail.com',
        subject: "Status of the pipeline: ${currentBuild.fullDisplayName}",
        body: "${env.BUILD_URL} has result ${currentBuild.result}" 
    }
}