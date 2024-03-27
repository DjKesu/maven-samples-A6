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

    stage('bisect start') {
      steps {
        sh 'git bisect start 26438de182f7a00147b5e53e9408a3c3745ca509 34d31973a0cc1f3d77cd5038fc9c01eeba7ec183'
      }
    }
    stage('bisect run') {
      steps {
        sh 'git bisect run'
      }
    }

  }
}
