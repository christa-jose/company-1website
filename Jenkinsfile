pipeline{
  agent any
  stages{
    stage('Stop old Container'){
      steps{
        bat 'docker rm -f company-1website || exit 0'
      }
    }
    stage('Checkout Code'){
      steps{
        echo 'Puling code from Github'
        checkout scm
      }
  }
    stage ('Build Docker Image'){
      steps{
        echo 'Building Docker Image'
        bat 'docker build -t company-1website .'
        
      }
    }
    stage ('Run docker container')
    {
      steps{
        echo 'Running Docker container'
        bat 'docker run -d -p 8070:80 company-1website'
      }
    }
}
}
