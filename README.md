### What is this repository for? ###

This repository is an eks-deploy workflow template for all projects. Workflow templates can be used to create new workflows in an organizations' public repositories; to use templates to create workflows in private repositories, the organization must be part of an enterprise or GitHub One plan which MagicMemories is not yet.
The eks-deploy-template.yml template does the following:

#### Basic workflow: ####

1) "build_and_test" job run on each push to a branch and pull requests against the main branch.
2) "publish_image" job run on each push to a branch and pull requests against the main branch.
3) "deploy_to_test_env" and deploy_to_test_uat" job runs on every merge to main branch.
4) at the end of each job a coverage report will be generated :codacy-coverage-reporter

#### The KNOWNS ####
1) By default images will be pushed to docker.mm (Nexus) and 482780835707.dkr.ecr.us-west-2.amazonaws.com.
2) All the secret values are stored either as Organizational Secrets or Repository Secrets.  eg: ${{ secrets.AWS_ACCESS_KEY_ID }}

#### Get notifications about your project ####
1) To get notification about the projects you are working on, navigate to slack.
2) Click on GitHub under "App" in slack and type: `/github subscribe magicmemories/{repo_name_for_notification} 
3) You will get notified of success/failures/pull requests to only those repositories you "subscribe" to.
