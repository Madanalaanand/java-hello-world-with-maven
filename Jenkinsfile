node('jdk11-mvn3.8.4') {
    git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
     archiveArtifacts artifacts: 'target/surefire-reports/*.xml', followSymlinks: false
     archiveArtifacts artifacts: '**/TEST-*.xml', followSymlinks: false
}