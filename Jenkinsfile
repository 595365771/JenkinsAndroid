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
        git(branch: 'master',  
          url: 'https://github.com/595365771/StickyRecyclerView.git',  
            credentialsId: '1001' // 替换为你在 Jenkins 中设置的凭据ID
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
      // 总是存档构建成品
      archiveArtifacts '/Users/shiyiheng/.jenkins/workspace/JenkinsAndroid_main/app/build/outputs/apk/release/*'
    }
}
}
