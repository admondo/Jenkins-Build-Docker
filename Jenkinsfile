node {
deff app
stage ('clone') {
checkout scm
}
stage ('Build') {
app=docker.build ("xavki/nginx") 
}
stage ('Test')
docker.image ("xavki/nginx").withRun ('-p 8080:80') { c->
sh 'docker ps'
sh 'curl -s http://localhost:8080'
}
}
}
