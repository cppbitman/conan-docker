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
        sh 'pip install conan --upgrade'
        sh 'git clone https://github.com/conan-community/conan-openssl'
        sh 'cd conan-openssl'
        sh 'conan create . user/channel'
      }
    }
  }
}
