pipeline {
	agent any 
	stages{
	     stage("clean"){
	      steps {
	          cleanWs()
	      }
	  }

	  stage("clone") {
	   steps {
	     git branch: 'main', url: 'https://github.com/ArshiyaIrshad/sample-html-app.git'
	     sh "ls"
	   }
	  }
        stage("docker image") {
       steps{
        sh "docker build -t arshiyairshad/html-app ."
      }
     }
     stage("dockerhub"){
         steps{
             sh "docker login -u arshiyairshad -p arsh@507807"
             sh "docker push arshiyairshad/html-app"
         }
     }
     stage("docker container") {
         steps{
             sh "docker rm -f html-app"
             sh "docker run -d --name html-app -p 82:80 arshiyairshad/html-app"
         }
     }
} }
