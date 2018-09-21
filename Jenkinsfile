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
        sh '''pwd && git clone https://github.com/conan-community/conan-openssl &&
        cd conan-openssl && pwd && conan create . user/channel'''
      }
    }
  }
}
