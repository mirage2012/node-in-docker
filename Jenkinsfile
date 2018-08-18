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

  stage('Deploy approval'){
    input "Deploy to K8sS"
}
  stage('Deploy to K8s') {
   sh 'kubectl set image deployment/nodeapp nodeapp=us.gcr.io/caramel-graph-209306/nodeapp:latest'
  }
}
  }
