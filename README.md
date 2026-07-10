<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://nextwork.ai/projects/aws-security-iam)

**Author:** Tomislav Pandza  
**Email:** pandza.tomislav@gmail.com

---

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

We'll launch an EC2 instance, then control who has access to it by creating some IAM policies and user groups.

### Tools and concepts

Services I used were EC2 and IAM Policy. Key concepts I learnt include creating an intern account, assigning a policy to that accout which in this case was the ability to only be able to work on the Development instance however to not be able to stop it.

### Project reflection

The project took about an hour to finish.

---

## Tags

### What I did in this step

In this step, I will launch an EC2 instance as we need more computing power of our website to match the increased traffic on our site.

### Understanding tags

Tags are like labels you can attach to AWS resources for organization.

In this case, we're creating a tag called "Env" with a value of "production" or "development" to label the instances used in production vs development environments

### My tag configuration

The tag I’ve used on my EC2 instances is called Env and the values I’ve assigned for my instances are production and development

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will use the AWS IAM to give access to our intern to the development instance only.

### Understanding IAM policies

IAM Policies are designed to manage access to your resources in AWS. Giving permissions to your IAM groups, users or roles and what they can do or not do with certain resources and when they kick in

### The policy I set up

For this project, I’ve set up a policy using JSON

### Policy effect

I’ve created a policy that allows any action in the EC2 instance with the limit to the Development resources tag as again, we do not want any issues with the production resource.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy mean - Effect (allow or deny a certain action inside the policy), Action (which specific actions are allowed inside the policy) and Resource (which resource does the policy apply to).

---

## My JSON Policy

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will simplify the login by using an Account Alias

### Understanding account aliases

An Account Alias is a friendly name for your AWS account that you can use instead of your account ID (which is usually a bunch of digits) to sign in to the AWS Management Console.

### Setting up my account alias

Creating an account alias took me a few minutes only

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will create an IAM group for all NextWork interns, so I can manage all interns' permissions from one place and an IAM user for our new intern, so they have a way to log in.

### Understanding user groups

IAM user groups are  are the collections/folders of users for easier user management.

### Attaching policies to user groups

I attached the policy I created to this user group, which means granting the permissions associated with that group.

### Understanding IAM users

IAM users are the people that will get access to your resources/AWS account.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is via email directly or via csv file

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed there was an immediate denied access to some of the services. Like applications, cost & usage ans security

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will log in into the intern's user account and test what we have access to.

### Testing policy actions

I tested my JSON IAM policy by trying to stop the instance.

### Stopping the production instance

When I tried to stop the production instance an error page opped up. This was because the stop protection was on which does not allow them to stop any instance

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance on the intern user, it did not work as the stop protection was on. I had to disable the stop protection to be able to stop the instance. The protection was there so the intern does not do any demage to the AWS environment

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to use another way to validate the policy through Policy Simulator. I'm doing this because this way we do not disrupt other engineers and users.

### Understanding the IAM Policy Simulator

The usage of IAM Policy Simulator is preferred as it gives you the ability to test the given access to your users in the group without having to disturb the actual resources and your users inside.

### How I used the simulator

The results at first were denied for both changing the tags  and stoping instance. I had to adjust that to only one instance which was the development istance as othervise the system thought it was assigning the stop instane to all of the resources.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-security-iam_069d8a621)

---

---
