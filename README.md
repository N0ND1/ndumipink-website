# ndumipink-website
AWS S3 static website
🚀 Steps I Took

Created an S3 Bucket
Bucket name: ndumipink
Disabled “Block all public access” so the bucket can be accessed via the S3 URL.
Created Website File
Wrote an HTML file containing the code for the Pink Strawberry Macaron website.
Saved the file as index.html.
Uploaded File to S3
Uploaded the index.html file into the ndumipink bucket.
Configured Permissions
Went to Permissions and updated the bucket policy to allow public access to the index.html file.
Ensured that the bucket name in the JSON policy matched the actual bucket name (ndumipink).
Enabled Static Website Hosting
Turned on Static Website Hosting.
Set the index document to index.html.
Got the website endpoint URL from S3.
Tested the Website
Opened the URL in Chrome to confirm the site was working.

⚠️ Errors I Faced & Fixes
404 Not Found (NoSuchKey)
Problem: The index.html file name was not correct or didn’t match.
Fix: Checked and made sure the file name was exactly index.html (case-sensitive).
Bucket Policy Error
Problem: The S3 bucket name in the bucket policy JSON did not match the actual name (ndumipink).
Fix: Updated the policy JSON so the bucket name was correct.
URL Not Accessible by Others
Problem: At first, only I could open the URL and others could not.
Fix: Made sure block public access was turned off and that the bucket policy allowed public read access (s3:GetObject).
After fixing these issues, I was able to access the site and so could others using the public S3 endpoint.

📂 Project Structure
ndumipink/
│── index.html   # Pink Strawberry Macaron website
│── README.md    # Documentation of the project

📜 Correct Bucket Policy

Here’s the bucket policy I used to make the website public:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::ndumipink/*"
    }
  ]
}

✅ Final Result

The static website was successfully deployed on AWS S3 and works through the public endpoint link. 🎉
