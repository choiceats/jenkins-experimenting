node {
  stage("remove_old_containers") {
    sh "docker stop apache-name-test || true"
    sh "docker rm apache-name-test || true"
  }

  checkout scm

  def customImage = docker.build("apache-tag")
  // agent { dockerfile true }

  try {

    //    stage('checkout') {
    //      checkout scm
    //    }
    //    stage('prepare') {
    //      sh "git clean -fdx"
    //    }
    // stage('copy_files') {
    //   sh "mkdir build/"
    //   sh "cp -R src/* build/"
    //   sh "echo files in build/"
    //   sh "ls build/"
    // }

    stage("run_container") {
      sh "docker run -p 80:80 -dit --name apache-name-test apache-tag"
    }

    //    stage('compile') {
    //      echo "nothing to compile for hello.sh..."
    //    }
    //    stage('test') {
    //      sh "./test_hello.sh"
    //    }
    //    stage('package') {
    //      sh "tar -cvzf hello.tar.gz hello.sh"
    //    }
    //    stage('publish') {
    //      echo "uploading package..."
    //    }

  } finally {
    stage('cleanup') {
      echo "doing some cleanup..."
    }
  }
}
