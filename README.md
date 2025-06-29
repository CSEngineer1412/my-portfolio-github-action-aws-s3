# my-portfolio-github-action-aws-s3
My Portfolio Deployment on AWS S3 using GitHub Actions (CI/CD Pipeline)

📊 CI/CD Workflow Diagram

┌────────────┐      Push Code     ┌───────────────┐
│  Developer │ ──────────────────►│ GitHub Repo   │
└────────────┘                    └───────────────┘
                                       │
                                       ▼
                          ┌────────────────────────┐
                          │ GitHub Actions Workflow│
                          └────────────────────────┘
                                       │
                                       ▼
                          ┌────────────────────────┐
                          │ AWS S3 (Static Hosting)│
                          └────────────────────────┘
                                       │
                                       ▼
                          http://<bucket>.s3-website-<region>.amazonaws.com
                

## 🔧 Tech Used

- HTML/CSS/JavaScript
- GitHub Actions (CI/CD)
- AWS S3 for static hosting

## 🚀 How it works

1. Push to `main` branch
2. GitHub Action triggers
3. Site is deployed to your S3 bucket

## ✅ Prerequisites

- AWS S3 bucket with static website hosting
- GitHub repo secrets:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `AWS_REGION`
  - `S3_BUCKET`

🔹 Step-by-Step Setup
✅ 1. Create an S3 Bucket for Static Hosting
Go to AWS → S3 → Create Bucket

Name: my-webapp-bucket

Uncheck “Block all public access”

Enable Static Website Hosting:

Index document: index.html

Save the bucket name and region

✅ 2. Create IAM User for GitHub Access
IAM → Users → Create user: github-s3-deploy

Attach policy: AmazonS3FullAccess

Save the Access Key ID and Secret Access Key

🔐 Best practice: Use fine-grained permissions and limit to just this bucket in production.

✅ 3. Add Secrets to GitHub
Go to your GitHub repo → Settings → Secrets → Actions:

AWS_ACCESS_KEY_ID → your IAM access key

AWS_SECRET_ACCESS_KEY → your IAM secret key

🌐 Access the Website
Go to S3 → your bucket → Properties → Static Website Hosting
Use the Bucket Website URL.

## ✅ For References https://www.youtube.com/watch?v=zPwMnGMEL3Y

