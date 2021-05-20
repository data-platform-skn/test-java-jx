pipeline {
  agent any
  stages {
    stage('Build Pack Run') {
      steps {
        script {
          sh 'pack build demo-image --builder gcr.io/buildpacks/builder:v1'
        }

      }
    }

    stage('Build pack complete') {
      steps {
        script {
          sh 'echo "Done"'
        }

      }
    }

    stage('Docker List Image') {
      steps {
        script {
          sh 'docker images ls'
        }

      }
    }

    stage('ECR Login') {
      steps {
        script {
          sh '\$(aws ecr get-login)'
        }

      }
    }

  }
}