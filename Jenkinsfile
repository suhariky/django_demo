pipeline{
    agent any
    environment{
        IMAGE_NAME = "qwerty112358/django_jenkins"
    }
    stages{
        stage("build"){
            steps{
                build job: "/lib/django build parametrized/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}"),
                    string(name: 'IMAGE_NAME', value: "${IMAGE_NAME}"),
                    string(name: 'GIT_COMMIT_HASH', value: "${GIT_COMMIT}")
                ]
            }
        }
        stage("test"){
            steps{
                build job: "/lib/django-test-parametrized/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}")
                ]
            }
        }
        stage("push"){
		steps{
			withCredentials([usernamePassword(credentialsId: 'docker_pass', usernameVariable: 
			'USERNAME', passwordVariable: 'PASSWORD')]) {
				sh 'docker login -u ${USERNAME} -p ${PASSWORD}'
				sh 'docker push ${IMAGE_NAME}:${GIT_COMMIT}'
				sh 'docker push ${IMAGE_NAME}:latest'
			}	
		}
	}
    }
}
