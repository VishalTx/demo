node {
    def app

    stage('Clone repository') {
      
      
        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("vishal7500/sader")
    }

    // stage('Test image') {
  

    //     app.inside {
    //         sh 'echo "Tests passed"'
    //     }
    // }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
            app.push("${env.BUILD_NUMBER}")
        }
    }