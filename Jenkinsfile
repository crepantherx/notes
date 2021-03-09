pipeline {
    agent any
    stages {
	    stage('Build') { // build and tag docker image
		steps {
		    	script {  
				sh "docker push crepantherx.jfrog.io/techmahindra-docker-dev-local/todo:v1.0.${env.BUILD_ID}"
		    	}
		}
	    }

	    stage('Upload'){
		steps {
			script {  
				docker.withRegistry('https://crepantherx.jfrog.io', 'jfrog') {
					sh "docker push crepantherx.jfrog.io/techmahindra-docker-dev-local/todo:v1.0.${env.BUILD_ID}"
				}
			}
		}
	    }
    }
}
