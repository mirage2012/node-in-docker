node {
  stage 'Checkout'
  git 'https://github.com/mirage2012/node-in-docker.git'
 
  stage 'Docker build'
  docker.build('demo')
  stage 'Docker push'
  docker.withRegistry('https://us.gcr.io') {
    docker.image('demo').push('latest')
  }
 
  
}
