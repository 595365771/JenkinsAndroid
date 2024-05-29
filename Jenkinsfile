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
            credentialsId: '1001' // 替换为你在 Jenkins 中设置的凭据ID
           )
      }
      //  steps {
      //   echo 'Checkout Successful'
      // }
    }

    stage('Build') {
      steps {
        sh 'chmod +x ./gradlew'
        sh './gradlew clean build'
      }
      // steps {
      //   echo 'Android build complete'
      // }
    }

  }
  post {
    always {
      // echo 'Android build complete'
      always {
        // 总是存档构建成品
        archiveArtifacts '/Users/shiyiheng/.jenkins/workspace/JenkinsAndroid_main/app/build/outputs/apk/release/*'
      }
    }
  }
}
