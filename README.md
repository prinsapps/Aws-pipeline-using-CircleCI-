# mymeetup Aws Deploying through circleci


Live Link aws - https://mymeetup.s3.eu-west-2.amazonaws.com/index.html 

Steps
Let's get started:

Create a GitHub repository containing a hello world html file (optional: that links a css file to change font size).
Use the AWS Management Console to create a AWS S3 storage bucket that will hold the website's files. You need to pick a globally unique bucket name, you can skip the tags screen but you need to unselect the "Block public access policies" - so you can write a public access policy later on.
Lets setup a Deployment Pipeline - What is this? - It's a pipeline of steps required to deploy software. Use Circleci to deploy all code changes to the S3 storage bucket when changed. Create a directory called .circleci in the root directory of your local GitHub repository. Create a config.yml file with the following content: example. Update the file to include your bucket name.
So it ran, what happened? Oh it failed! Click on the Red Error button and read the message and see if you can workout why it failed.
CircleCI was unable to locate credentials! What would it need credentials for?
Create a user in AWS Identity and Access Management (IAM) that is allowed to write into the S3 bucket and CircleCI will use this user. The user must have a policy attached allowing it to write to S3 - see if you can find out which policy you need?
In the CircleCI project find the Settings (Cog) and then the AWS Permissions put the Access key and Secret key you were given at the end of creating the user.
Update your S3 bucket in amazon to add a policy making the bucket publicly accessible. Don't forget to attach the bucket to the policy. You can browse the AWS Management Console S3 service to see the Policy is on the bucket. Example Policy
GO back to S3 and find the index.html file in your bucket - click on the bucket and find the public URL of the file, click it and view your website.
Commit and push changes to the repository that makes the webpage contain different content or link in a css file to style the page.
