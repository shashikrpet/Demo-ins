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

// stage('docker image'){
//   steps{
//     sh'docker build -t shashikrpet/demoins:1.0 .'
//   }
// }


stage('docker push'){
 steps{
  withCredentials([usernamePassword(credentialsId: 'dockerlog', passwordVariable: 'passlog', usernameVariable: 'userlog')]) {
    sh 'docker login -u ${userlog} -p ${passlog}'
} 
     sh ' docker push shashikrpet/demoins:1.0'
 }
}
    
  }
}

    
