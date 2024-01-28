pipeline{
  agent any
  tools{
    maven 'M2'
  }

  stages{
    stage('git checkout'){
    steps{
git branch: 'main', url: 'https://github.com/shashikrpet/Demo-ins.git'
    }
  }

    stage('maven'){
    steps{
      sh 'mvn clean package'
    }
    }

stage('docker image'){
  steps{
    sh'docker build -t shashikrpet/demoins:1.0 .'
  }
}
    
  }
}

    
