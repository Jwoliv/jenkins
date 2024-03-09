pipeline {
  agent any
  stages {
    stage("clean up") {
      steps {
        deleteDir()
      }
    }
    stage("build") {
      steps {
        sh "git clone https://github.com/Jwoliv/GeekShop.git"
        dir("GeekShop") {
          sh "mvn clean package"
        }
      }
    }
    stage("test") {
      steps {
        dir("GeekShop") {
          sh "mvn test"
        }
      }
    }
    stage("finish") {
      steps {
        echo "====================="
        ehco "job completed success"
        echo "====================="
      }
    }
  }
}