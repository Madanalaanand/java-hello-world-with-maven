node('jdk11-mvn3.8.4'){
try{
  stage('git') {
    git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
}
stage('build') {
   sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
}
stage('archive') {
     archiveArtifacts artifacts: 'target/surefire-reports/*.xml', followSymlinks: false
}
stage('archive') {
    archiveArtifacts artifacts: '**/TEST-*.xml', followSymlinks: false
}     

              currentbuild.result='SUCCESS'
}
catch (err){
              currentbuild.result='FAILURE'
} 
  finally{
     mail to: 'madanalaanand7@gmail.com'
     subject: "status of the pipeline: show",
     body: "${env.BUILD_URL} has result ${currentbuild.result}"
  }
}