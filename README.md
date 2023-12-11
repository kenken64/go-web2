# Github Actions CICD Workshop

This is an individual workshop.

Setup
1. Create the following accounts if you don’t already have them
a. GitHub - https://github.com/
b. Railway - https://railway.app/ . 

Please use my promo code https://railway.app?referralCode=PTGdkj
You will have to pay $5 a month for a subscription. You can cancel after the
assignment.

Another option is for 1 person to subscribe and a few of you share the
Account.

c. Join Slack channel - https://join.slack.com/t/bhutan-workshop/shared_invite/zt-28p878to4-v2kV1pFcb9aXTIJivuTa5g

2. Download the Golang application source. You will be using this code base for the workshop. The lecturer will provide you with the download link during class.

Create a git repository with this code. The initial visibility of your Git repository
must be PRIVATE viz. no one else can access it except you. This is to prevent
others from copying your work. If your assignment is plagiarized, you will be
considered as a willing party in the aiding and abetting of this dishonest act.

## Assignment

In this assignment, you will be writing a CI/CD pipeline to deploy a Golang
application to Railway and publish the deployment URL on Slack. Your pipeline is
to perform the following tasks:

1. The pipeline should be triggered when a branch name with the following
format v<digit>.<digit>. For example, if you push a branch with the
following names v1.0, v15.3 or v7.09, it should trigger your workflow but
not v0.1-beta, v0.1.1 or feature-01.

2. Deploy the application to Railway. Create a new project for the deployment.

3. Create a release using the branch name; for example, if you push a branch
with the following name v1.0, then the workflow should create a release
called v1.0.

4. Send a notification to Slack. The notification should include all the following
information in the following order.
    a. Name 
    b. Repository – this is the repository of your work; the URL should be derived from github context and not hard coded into the workflow.
    c. Deployment URL – your Railway service URL. You should not hardcode this into your workflow.

The Slack notification should include a clickable link, Open Application, that
opens your application on the browser with the deployment URL


5. The pipeline should not run if the commit message starts with #NORUN even if
the branch name has the correct pattern. For example, the following push will
not trigger your workflow

```
git commit -m “#NORUN fixed typo in README.md”
git push origin v1.0
```

The Slack workspace is set up to receive notifications as Incoming
Webhook. The following two webhook have been set up in the Slack
workspace and is associated with the following channels

test-submission

https://hooks.slack.com/services/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

Use test-submission channel when you are testing your workflow.

Important: Do not expose the above 2 webhook URL in your git repository by
hardcoding them into the workflow. If you do that Slack will disable the
webhooks. When you try to send the notification, you will get an unauthorized message. The webhook will not be re-enable in the event that they are disabled1.

All sensitive information should be configured and used as GitHub secrets.

Git Actions
The following is a list of minimum git actions you will be using. Feel free to use alternatives or other git actions that you believe are more suited for your requirements.

Checkout - https://github.com/marketplace/actions/checkout
Create tag - https://github.com/rickstaa/action-create-tag
Create release - https://github.com/marketplace/actions/create-release
Slack notification - https://github.com/marketplace/actions/slack-send. 

See the following document for creating and formatting Slack notifications
https://api.slack.com/messaging/composing/layouts

## Submission
Submit the workshop by pushing it to your GitHub repository; this should be the
same repository as your Slack notification.

1 The purpose of this is to impress on you the consequences of bad software development habits when it comes to handling sensitive information. If you adopt bad habits, the repercussions can be felt not only by you, but your coworkers as well.Version 2



# Go-web Project

```
go mod init go-web2

```

```
go mod tidy
```

```
go build
```

```
git merge v1.1
```
