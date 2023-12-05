
## Features

Before you begin, ensure you have the following:

- An AWS account with appropriate permissions to create and manage S3 buckets.
- AWS CLI installed and configured with the necessary credentials.

## Getting Started

Follow these steps to set up and deploy your static website:

### 1.Clone the repository to your local machine:

```
git clone https://github.com/NirmalNaveen20/s3-static-website.git
```

### 2.Customize your website content:

Replace the contents of the index.html, style.css, and any other necessary files in the public directory with your own website content.

### 3.Create an S3 bucket:
```
aws s3api create-bucket --bucket your-unique-bucket-name --region your-preferred-region
```

Make sure to replace your-unique-bucket-name with a globally unique name for your bucket and your-preferred-region with the AWS region where you want to create the bucket.

### 4.Upload your website files to the S3 bucket:
```
aws s3 sync public/ s3://your-unique-bucket-name
```

### 5.Enable static website hosting on the S3 bucket:


```
aws s3 website s3://your-unique-bucket-name/ --index-document index.html
```
Update the index.html with the actual name of your main HTML file if it's different.

### 6.Access your static website:

After a few minutes, your website should be accessible at the following endpoint:



    http://your-unique-bucket-name.s3-website-your-preferred-region.amazonaws.com

    Replace your-unique-bucket-name and your-preferred-region with the appropriate values.


Cleanup

To delete the S3 bucket and associated resources:

```
aws s3 rb s3://your-unique-bucket-name --force
```

Note: Deleting a bucket will permanently remove all objects stored in the bucket.
