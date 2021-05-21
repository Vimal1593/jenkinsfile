pipeline{
  agent any
  environment {
  PATH = "{$path}:${getTerraformPath()}"
}

stages{
  stage('terraform init'){
    steps{
      sh 'terraform init'
      sh 'terraform apply -auto-approve'
    }
  }
  stage('jenkins build alerts'){
   steps{
  slackSend(channel: '#jenkinsit', color: '#009933', message: 'job1 build sucessful')
  }
  }
  }
  }
  def getTerraformPath(){
  tfHome = tool name: 'terraform 0.15', type: 'terraform'
  return tfHome
  }
