pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        script {
          sh 'pack build demo-image --builder gcr.io/buildpacks/builder:v1'
          sh 'echo "Done"'
        }

      }
    }

  }
}