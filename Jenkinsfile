pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-west-2',credentials:'aws-static') {
          s3Delete(bucket: 'walabs-shewit-staticrepo', path:'')
          s3Upload(file: 'index.html', bucket: 'walabs-shewit-staticrepo', path:'index.html')
        }
      }
    }
  }
}