pipeline {
  agent {
    docker {
      image 'lasote/conangcc7'
      args '-it --rm'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'git --version'
        sh 'sudo pip install conan --upgrade'
        sh '''pwd && rm -rf conan-openssl && git clone https://github.com/conan-community/conan-openssl &&
        cd conan-openssl && pwd && conan create . user/channel && ls &&
        conan remote add artifactory http://172.16.64.65:8081/artifactory/api/conan/conan-local &&
        conan upload "*" -r artifactory --all --confirm
        '''
      }
    }
  }
}
