pipeline {
  environment {
    registry = '890324431850.dkr.ecr.ap-south-1.amazonaws.com/demo'
    registryCredential = 'AWS-ECR'
    dockerImage = ''
    imageName = 'demo'
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



       stage('Deploy image') {
        steps{
            script{
                dockerImage = docker.build imageName
                docker.withRegistry("https://" + registry, "ecr:ap-south-1:" + registryCredential) {
                   dockerImage.push('latest')
                }
            }
        }

  }
}
}
