node('jdk11-mvn3.8.4') {
    stage('git') {
    git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
   }
    stage('build') {
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
   }
     archiveArtifacts artifacts: 'target/surefire/*.xml', followSymlinks: false
}