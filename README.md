# Static Website Hosting on AWS S3
This project demonstrates how I created and deployed a static website using GitHub, Git, VS Code, and AWS S3. The goal was to build a simple static site locally, manage the source code using version control, and host it on the cloud.

## Project Overview
In this project, I developed a static website using HTML and CSS.  I used Visual Studio Code as my development environment and Git for version control. The project repository was synchronized with GitHub to store the code remotely and track changes. Finally, the website was deployed to the cloud using an AWS S3 bucket configured for static website hosting.

## Development Environment Setup
I started by installing and configuring the following tools:
- Git for version control
- VS Code (Visual Studio Code) as the code editor
- GitHub for remote repository hosting

## Steps

1. Created a project folder locally.
2. Opened the folder in VS Code.
3. Initialized a Git repository:
git init
4. Created the website files such as:
index.html
style.css
5. Added the files to Git and made the first commit:
git add .
git commit -m "Initial website commit"

## Synchronizing Git, GitHub, and VS Code

To store the project online and enable version tracking, I connected the local Git repository to GitHub.
### Steps
1. Created a new repository on GitHub.
2. Linked the local project to the remote repository: git remote add origin https://github.com/username/repository-name.git
3. Pushed the project to GitHub: git branch -M main
git push -u origin main

Now the project is synchronized between:
- Local machine (VS Code + Git)
- Remote repository (GitHub)

Any changes made locally can be committed and pushed to GitHub to keep the project updated

## Deploying the Website to AWS S3
After finishing the website development, I deployed it to Amazon S3 for cloud hosting.
## Steps
1. Logged into the AWS Management Console.
2. Navigated to Amazon S3.
3. Created a new S3 bucket.
4. Disabled Block Public Access to allow the website to be publicly accessible.
5. Enabled Static Website Hosting in the bucket properties.
6. Set the index document to: index.html
7. Uploaded all website files (index.html) to the bucket.
8. Updated the bucket policy to allow public read access.

Example policy:
```
{
 "Version": "2012-10-17",
 "Statement": [
 
  {
     "Sid": "PublicReadAccess",
     "Effect": "Allow",
     "Principal": "*",
     "Action": "s3:GetObject",
     "Resource": "arn:aws:s3:::my-bucket-name/*"
   }
 ]
}
```
## Accessing the Website
Once hosting was enabled, AWS generated a static website endpoint URL. The website can be accessed directly through this URL in a browser.
Example:
http://my-bucket-name.s3-website-region.amazonaws.com

## Conclusion 
This project demonstrates a simple workflow for building and deploying a static website using modern development tools and cloud infrastructure. By combining Git for version control, GitHub for repository management, and AWS S3 for hosting, it is possible to create a scalable and easily maintainable static web deployment pipeline.

