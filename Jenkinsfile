node {
  checkout(scm)

  try {
    //    stage('checkout') {
    //      checkout scm
    //    }
    //    stage('prepare') {
    //      sh "git clean -fdx"
    //    }
    stage('copy_files') {
      sh "cp src/* build/"
      sh "echo files in build/"
      sh "ls build/"
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
