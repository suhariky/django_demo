pipeline{
    agent any
    stages{
        stage("test"){
            steps{
                build job: "/lib/django-test-parametrized/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}")
                ]
            }
        }
        stage("build"){
            steps{
                build job: "/lib/django%20build%20parametrized/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}"),
                    string(name: 'IMAGE_NAME', value: "${IMAGE_NAME}")
                ]
            }
        }
    }
}
