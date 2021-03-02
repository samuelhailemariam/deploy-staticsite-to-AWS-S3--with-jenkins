pipeline {
  agent any
  stages {
      stage('Lint HTML') {
        steps {
          sh 'tidy -q -e *.html'
        }
      }
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