node {
def app
stage ('clone') {
checkout scm
}
stage ('Build image') {
app=docker.build ("xavki/nginx") 
}
stage('Test') {
docker.image("xavki/nginx").withRun('-p 8081:80') { c ->
sh 'sleep 5'  // Attendre 5 secondes
 sh 'curl -s http://localhost:8081'
    }
}

}
