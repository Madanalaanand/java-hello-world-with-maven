node('jdk11-mvn3.8.4'){
try{
  stage('git') {
    git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
}
stage('build') {
   sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
}
stage('archive') {
     archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
}
stage('publish test reports') {
    junit '**/TEST-*.xml'
}     

              currentbuild.result='SUCCESS'
}
catch (err){
              currentbuild.result='FAILURE'
} 
  finally{
     mail to: 'madanalaanand7@gmail.com',
     subject: "status of the pipeline: ${currentBuild.fullDisplayName}",
     body: "${env.BUILD_URL} has result ${currentbuild.result}"
  }
}