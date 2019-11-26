node {
    def app

    stage('Checkout from repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("learntechpuzz/demo-calculator-ui")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}



