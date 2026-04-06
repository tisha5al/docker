pipeline{
  agent any
  stages{
    stage('1 checkout'){
      steps{
        git url:'https://github.com/tisha5al/docker',branch:'main'
      }
    }
    stage('2 Build Image'){
      steps{
        bat 'docker build -t Mywebsite .'
      }
    }
    stage('3.stop/Remove old containers'){
      steps{
        bat 'docker stop Mycont || exit 0'
        bat 'docker rm Mycont||exit 0'
      }
    }
    stage('Run the image- Containerize'){
      steps{
        bat 'docker run -d -p 5000:80 --name Mycont Mywebsite'
      }
    }
  }
}
