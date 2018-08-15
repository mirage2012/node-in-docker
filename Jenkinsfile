
  node {
  stage 'Checkout'
  git 'https://github.com/mirage2012/node-in-docker.git'
    
  stage('Build image') {
  app = docker.build("caramel-graph-209306/nodeapp")
}
 stage('Push image') {
  docker.withRegistry('https://us.gcr.io', 'gcr:GCR') {
    app.push("${env.BUILD_NUMBER}")
    app.push("latest")
  }
}
  }
