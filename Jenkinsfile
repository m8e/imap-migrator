node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */
        checkout scm
    }

    stage('Copy dir') {
        sh "cp -r code build_migrator/rootfs"
    }

    stage('Build image') {
        app = docker.build("nutellinoit/imap-migrator","--pull build_migrator/")
    }

    stage('Delete dir') {
        sh "rm -rf build_migrator/rootfs || true"
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
