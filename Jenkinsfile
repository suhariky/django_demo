pipeline{
    agent any
    stages{
        stage("test"){
            steps{
                build job: "/Сухорукова%20Мария/django%20repo/",
                parameters: [
                    string(name: 'GIT_URL', value: "${GIT_URL}"),
                    string(name: 'GIT_BRANCH', value: "${GIT_BRANCH}")
                ]
            }
        }
    }
}
