@Library('jenkins-shared-library') _

def configMap = [
    project  : "roboshop",
    component: "catalogue"
]

if (env.BRANCH_NAME != 'main') {
    echo "Branch is ${env.BRANCH_NAME}. Continuing the pipeline..."
    nodejsPipeline(configMap)
} else {
    echo "Main branch detected. Aborting the pipeline."
    currentBuild.result = 'ABORTED'
    error("Pipeline is not allowed to run on the main branch.")
}