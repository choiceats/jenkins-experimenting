node {
  stage("remove_old_containers") {
    // sh "docker kill apache-tag"
    // sh "docker rm apache-tag"
  }

  checkout scm

  def customImage = docker.build("apache-name-test", "-f ${Dockerfile} -t apache-tag")
  agent { dockerfile true }

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
      sh "docker run -p 80:4000 -dit --name apahe-name-test apache-tag"
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
