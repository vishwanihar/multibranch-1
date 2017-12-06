properties([[$class: 'GithubProjectProperty', displayName: '', projectUrlStr: 'https://github.com/syamsundarreddy78/multibranch.git'],
            pipelineTriggers([
                        $class: "GithubPushTrigger",
		triggerOnPush: true,
		triggerOnMergeRequest: true,
		triggerOpenMergeRequestOnPush: "both",
		triggerOnNoteRequest: true,
		noteRegex: "REBUILD!",
		skipWorkInProgressMergeRequest: true,
		ciSkip: false,
		setBuildDescription: true,
		addNoteOnMergeRequest: true,
		addCiMessage: true,
		addVoteOnMergeRequest: true,
		acceptMergeRequestOnSuccess: false,
		branchFilterType: "NameBasedFilter",
		targetBranchRegex: "master",
		includeBranchesSpec: "master",
		excludeBranchesSpec: ""])])
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
                echo 'Testing.............'
            }
        }
        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploying....'
            }
        }
      }
}
