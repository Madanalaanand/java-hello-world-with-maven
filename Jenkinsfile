node('jdk11-mvn3.8.4') {
   stage('git') {
     git 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
  }
  stage('build'){
       sh'''
        echo "PATH=${PATH}"
        echo "M2_HOME=${M2_HOME}"

        '''
    
     sh '/usr/local/apache-maven3.8.4/bin/mvn clean package'
}
}