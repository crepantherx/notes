pipeline {
    agent any
    stages {
	    stage('Build image') { // build and tag docker image
        steps {
            echo 'Starting to build docker image'
		script {  
			docker.withRegistry('https://crepantherx.jfrog.io', 'jfrog') {
        			sh "docker build -t crepantherx.jfrog.io/techmahindra-docker-dev-local/todo:${env.BUILD_ID} ."
				sh "docker push crepantherx.jfrog.io/techmahindra-docker-dev-local/todo:${env.BUILD_ID}"
    			}

		}
        }
    }

	    stage('Deploying'){

		steps {
			echo 'Deploy'
        }
	    }


    }
}
