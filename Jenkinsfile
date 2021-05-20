pipeline {
  agent any
  stages {
    stage('') {
      steps {
        sh '''sh \'pack build demo-image --builder gcr.io/buildpacks/builder:v1\'
               sh \'echo "Done"\''''
        sh 'sh \'docker images list\''
      }
    }

  }
}