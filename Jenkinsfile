pipeline{
    agent any
    stages{
        stage("test"){
            steps{
                build job: "https://jenkins.mshp-devops.com/job/lib/job/django-test-parametrized/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}")
                ]
            }
        }
    }
}