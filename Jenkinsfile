pipeline {
  agent {
    node {
      label 'Android'
    }

  }
  stages {
    stage('initiate') {
      steps {
        echo 'Android build initiate'
      }
    }

    stage('Checkout') {
      steps {
        git(branch: 'master', url: 'https://github.com/595365771/StickyRecyclerView.git', credentialsId: '1001', changelog: true, poll: true)
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
      archiveArtifacts '/Users/shiyiheng/.jenkins/workspace/JenkinsAndroid_main/app/build/outputs/apk/release/*'
    }

  }
}