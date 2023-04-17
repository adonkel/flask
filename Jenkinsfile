pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/adonkel/flask', branch: 'main')
      }
    }

    stage('Build/Shell Script') {
      steps {
        sh 'docker build -t adonkel/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u adonkel -p dckr_pat_mEoSvd_rFVc7Pau5k2hPyn--6u8'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push adonkel/flask_app'
      }
    }

  }
}