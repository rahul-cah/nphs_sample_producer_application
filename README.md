# Base template for Cardinal Health project #
### STEP 1- SETTING THE STATUS CHECK PIPELINE TO RUN - DONE ONLY ONCE ###
The folder structure contains a example of pipeline, branch-check-pipeline.yml,  to run on pull request.
Change the access_token and repository value in the branch-check-pipeline.yml file:
```
access_token: ((common.GIT_TOKEN_CV)) #THIS MUST BE THE DEVELOPER PERSONAL ACCES TOKEN NOT THE DEPLOY KEY
base_branch: master.  # leave ir set to  master so it can pick up th epull request
repository: ((GIT_REPO_NAME)) #must be just the name of the repository such as CardinalHealth/EARI-Greetings-service-RI
```
Upload the pipeline to Concourse under your team space; remember the name you give to the uploaded pipeline.

### STEP 2 - SETTING REVIEWERS ###
To add pull request reviewiers of your branch please update the CODEOWNERS file under .github folder.
These ownwers will be the default owners for  everything in this repository unless a later match takes precedence.
Add the gihub name of the reviewers prefixed by a "@" such as 
```
*       @cah-firstname-lastname      @cah-firstname2-lastname2      @cah-firstname3-lastname3
```

### STEP 3 - SETTING THE MASTER REPOSITORY RULE - REQUIRES REPO ADMIN ROLE ###
Go in the "Setting--> Branches" for your repository and click "Add Rule" under the "Branch Protection Rules".
Entry the following values in the form and save the changes.

![Pipeline](./doc/RepoSettings.png)

### STEP 4 - INITIALIZE COMMIT VALIDATION FOR TRACKING ISSUE
Run the **cah-repo-init** to initialize the git validations (hooks):
```
 *  `Window `: run the cah-repo-init.bat 
 *  `Linux/Mac`: run the cah-repo-init.sh 
```
YOUR REPOSITORY IS NOW READY FOR CI/CD AND PULL REQUEST !!!!!!!!!


### DEFAULT README.MD TEMPLATE UNDER HERE; EVERYTHING ABOVE THIS LINE CAN BE REMOVED AFTER INITIAL SETTING #####
----------------------------------------------------------------------------------------------------------------

# Project Title

One Paragraph of project description goes here

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Willie Cardinal** - *Initial work* - 

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.


## Acknowledgments

* Hat tip to https://gist.github.com/PurpleBooth

