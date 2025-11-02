pipeline {
  agent any
  tools {
    jdk 'JAVA_HOME'
    maven 'MAVEN_HOME'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B clean package -DskipTests'
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
      echo '✅ Build OK'
    }
    failure {
      echo '❌ Build KO'
    }
  }
}
