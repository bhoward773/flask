pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/bhoward773/flask.', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t partplannerb/flask_app .'
      }
    }

    stage('Docker login') {
      steps {
        sh 'docker login -u partyplannerb -p dckr_pat_zMpcTwL-kw0lpZ2IF-u4OYXIi6M'
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push partyplannerb/flask_app '
      }
    }

  }
}