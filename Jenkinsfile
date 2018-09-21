pipeline {
  agent {
    docker {
      image 'lasote/conangcc7'
      args '-it --rm -v/tmp/conan:/home/conan/project'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'git --version'
        sh 'sudo pip install conan --upgrade'
        sh 'pwd'
        sh 'git clone https://github.com/conan-community/conan-openssl'
        sh 'pwd'
        sh 'cd conan-openssl'
        sh 'pwd'
        sh 'conan create . user/channel'
      }
    }
  }
}
