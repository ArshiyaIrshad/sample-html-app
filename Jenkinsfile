node {
    stage("clone"){
        git branch: 'main', url: 'https://github.com/ArshiyaIrshad/sample-html-app.git'
        sh "ls"
        }
        
    stage("docker image"){
        sh "docker build -t arshiyairshad/html-app ."
    }
    stage("docker hub"){
        sh "docker login -u arshiyairshad -p arsh@507807"
        sh "docker push arshiyairshad/html-app"
    }
    stage("container"){
        sh "docker rm -f html-app"
        sh "docker run -d --name html-app -p 84:80 arshiyairshad/html-app"
    }
}
