pipeline{
    agent any
    environment{
        IMAGE_NAME = "qwerty112358/django_jenkins"
    }
    stages{
        stage("build"){
            steps{
                build job: "/lib/django%20build%20parametrized/",
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
    }
}
