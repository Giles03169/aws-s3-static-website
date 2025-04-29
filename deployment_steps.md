# Deployment Steps for AWS S3 Static Website

## 1. Create an S3 Bucket

- Go to AWS S3 console
- Click "Create bucket"
- Set bucket name (must be globally unique)
- Region: Select your preferred AWS region
- Uncheck "Block all public access"
- Confirm settings and create the bucket

## 2. Upload Website Files

- Upload `index.html` to the bucket

## 3. Enable Static Website Hosting

- Go to Properties → Static Website Hosting → Enable
- Hosting type: Host a static website
- Index document: `index.html`
- Save changes

## 4. Set Bucket Policy for Public Access

Paste the following policy (replacing `my-aws-bucket-giles/*):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-aws-bucket-giles/*"
    }
  ]
}
