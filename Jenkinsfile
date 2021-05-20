pipeline {
  environment {
    registry = '890324431850.dkr.ecr.ap-south-1.amazonaws.com/demo'
    registryCredential = 'AWS-ECR'
    dockerImage = ''
    imageName = 'demo-image'
  }
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

    stage('Building image') {
      steps{
        script {
          
        }
      }
    }


    stage('ECR Login') {
      steps {
        script {
          sh 'aws ecr get-login'
        }

      }
    }


       stage('Deploy image') {
        steps{
            script{
                docker.withRegistry("https://" + registry, "ecr:ap-south-1:" + registryCredential) {
                   docker.image(imageName).push('0.0.1')
                }
            }
        }

  }
}
}
