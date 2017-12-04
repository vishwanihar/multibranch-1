properties([[$class: 'GithubProjectProperty', displayName: '', projectUrlStr: 'https://github.com/VeridicSolutionsOrg/Veridic_NorthCarolina.git/'], pipelineTriggers([githubPush()])])
pipeline {
    agent any
        stages {
            stage('Build') {
                when {
                    expression {
                        "foo" == "bar"
                    }
                }
                steps {
                    echo 'Building'
                }
            }
        stage('Test') {
            when {
                environment name: 'JOB_NAME', value: 'foo'
            }
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            when {
                branch 'master'
            }
            stage('Deployed'){
                when{
                    branch 'Developer_1'
                }
            steps {
                echo 'Deploying'
            }
        }
    }
}
