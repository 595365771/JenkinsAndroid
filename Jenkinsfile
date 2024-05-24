pipeline {
  agent any
  stages {
    stage('initiate') {
      steps {
        echo 'Android build initiate'
      }
    }

    stage('Checkout') {
      steps {
        // checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/595365771/StickyRecyclerView.git']]])

        git(branch: 'master',  
            url: 'https://github.com/595365771/StickyRecyclerView.git',  
            credentialsId: '3001' // 替换为你在 Jenkins 中设置的凭据ID
           ) 
      }
    }

    stage('Build') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew clean build'
      }
    }

  }
  post {
    always {
      echo 'Android build complete'
    }

  }
}
