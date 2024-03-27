pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
   stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/DjKesu/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('run') {
      steps {
        sh 'mvn verify'
      }
    }
     stage('bisect') {
       steps {
         sh 'git bisect start 34d31973a0cc1f3d77cd5038fc9c01eeba7ec183 198644632661c67b6c32f59e9047c11a70685e15 & git bisect run'
     }
  }
}
