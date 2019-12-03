node {
    def app

    stage('Checkout') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("rasrividya/demo-calculator-ui")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhubcredentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}



