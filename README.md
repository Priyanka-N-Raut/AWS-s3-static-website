# AWS-s3-static-website
```
## Hosting s3 static website
```
## AWS S3 Static Website Hosting Guide
## 1. Create S3 Bucket
```
Go to AWS Management Console → S3.
Click Create bucket.
Enter a unique name (e.g., mybucketofawspriyanka).
Choose region (e.g., us-east-1).
Disable "Block all public access" under permissions.
Click Create bucket.
```
## 2. Upload Image
```
Open the newly created bucket.
Click Upload → Add files → Select cat.jpg from your computer.
Click Upload.
```
## 3. Update Bucket Policy
```
Go to Permissions tab of your bucket.
Click Bucket Policy → Paste the following:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::mybucketofawspriyanka/*"
    }
  ]
}

Click Save.
```
## 4. Upload index.html
```
Create a file named index.html with the following content:

<!DOCTYPE html>
<html>
<head>
    <title>My Static Website</title>
</head>
<body>
    <h1 style="text-align: center;">Welcome to My Static Website!</h1>

    <div style="text-align: center;">
        <img src="https://mybucketofawspriyanka.s3.us-east-1.amazonaws.com/cat.jpg" alt="cat image">
    </div>
</body>
</html>

Go to Objects tab.
Click Upload → Add files → Select index.html.
Click Upload.
```
## 5. Enable Static Website Hosting
```
Go to Properties tab.
Scroll to Static website hosting → Click Edit.
Enable "Static website hosting".
Set Index document: index.html.
Click Save changes.
```
## 6. Test Website
```
Go to Static website hosting section.
Copy the Endpoint URL (e.g., http://mybucketofawspriyanka.s3-website-us-east-1.amazonaws.com).
Open in browser → You should see your HTML page with cat.jpg displayed.
```

