if(!JENKINS_URL.contains('.jenkins.io')){
	node("utility-slave") {
    		checkout scm
    		docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
        		stage('Build and Deploy Docker Image') {
            			def docker4jcasc = docker.build("praqma/docker4jcasc:${env.BUILD_ID}", '--no-cache .')
            			docker4jcasc.push()
            			docker4jcasc.push('latest');
        		}		
    		}	
	}
}
