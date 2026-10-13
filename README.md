AWS S3 Static Website Hosting Project 

Project Summary 
This project demonstrates the deployment of a React/Vite website using Amazon S3 Static Website Hosting. The application was built locally, deployed to AWS S3, and configured for public access. During deployment, issues related to file structure and access permissions were identified and resolved. 

Technologies Used 
React 
Vite 
Amazon S3 
Git 
GitHub 
Deployment Process 
Built the application using npm run build. 
Generated a production-ready dist folder. 
Uploaded the build artifacts to an Amazon S3 bucket configured for Static Website Hosting. 
Configured index document settings. 
Validated website accessibility through the S3 website endpoint. 
Challenges Encountered 
Initially uploaded the dist folder instead of the contents of the dist folder. 
Website assets returned 403 Access Denied errors. 
React application displayed a blank page because JavaScript and CSS resources could not be loaded. 
Troubleshooting and Resolution 
Uploaded the contents of the dist directory directly to the root of the S3 bucket. 
Configured a bucket policy to allow public read access to bucket objects. 
Verified asset accessibility and confirmed successful loading of JavaScript and CSS files. 
Tested the application using browser developer tools and network inspection. 
Outcome 
Successfully deployed a fully functional static website on AWS S3. 
Resolved file structure and permission issues. 
Gained experience with cloud hosting, access control, and troubleshooting web deployments. 
 

Deployment Troubleshooting Screenshot 
Safari Network tab showing the 403 errors for JavaScript and CSS assets before the bucket policy was configured. 

 

Bucket Policy Fix Implemented 
The 403 Access Denied errors were resolved by applying the following S3 bucket policy, which grants public read access to all objects in the bucket: 
 

{ 
  "Version": "2012-10-17", 
  "Statement": [ 
    { 
      "Sid": "PublicReadGetObject", 
      "Effect": "Allow", 
      "Principal": "*", 
      "Action": "s3:GetObject", 
      "Resource": "arn:aws:s3:::website-project-dominic/*" 
    } 
  ] 
} 
 

Browser-Based Troubleshooting with Safari Developer Tools 
During troubleshooting, Safari Web Inspector was used to analyze network requests and identify why the website was displaying a blank page. The Network tab revealed that the HTML document loaded successfully (HTTP 200), while the JavaScript and CSS assets returned HTTP 403 Access Denied errors. This observation helped isolate the issue to S3 permissions rather than the React application code itself. 

 

Figure: Safari Web Inspector Network tab showing successful document loading alongside 403 errors for application assets. These errors indicated that the React application resources were blocked by S3 access controls and guided the implementation of the bucket policy fix. 

 

Successful Deployment Verification 
After implementing the S3 bucket policy and correcting the deployment structure, the React/Vite application loaded successfully through the Amazon S3 Static Website Hosting endpoint. The screenshot below demonstrates the fully functional website, confirming that JavaScript and CSS assets were loading correctly and that the deployment was successful. 

 

Figure: Successfully deployed portfolio website hosted on Amazon S3 Static Website Hosting. The application renders correctly after resolving asset permission issues and verifying public access to website resources. 

 

Project Attribution 
This project was completed using the AWS S3 Static Website Hosting lab provided by NextWork. The guided lab supplied the deployment objectives and AWS workflow. The React/Vite portfolio website deployed during this project was my own application, and additional troubleshooting was performed to resolve S3 access control and website asset loading issues. 

Personal Contributions 
Built and maintained the personal React/Vite portfolio website used for deployment. 
Deployed the application using Amazon S3 Static Website Hosting. 
Troubleshot 403 Access Denied errors affecting JavaScript and CSS assets. 
Used Safari Web Inspector to analyze network requests and identify failed resource loading. 
Implemented and validated an S3 bucket policy to provide public read access to website assets. 
Verified successful website operation after correcting file placement and access controls. 
 

Lab Objectives Completed 
Created an Amazon S3 bucket for static website hosting. 
Uploaded HTML, image, JavaScript, and CSS files to the S3 bucket. 
Configured Amazon S3 Static Website Hosting. 
Enabled public access to website content through S3 permissions and bucket policies. 
Deployed a personal React/Vite portfolio website using Amazon S3. 
Validated website accessibility through the S3 website endpoint. 
Used Safari Web Inspector to analyze network requests and troubleshoot website loading issues. 
Identified and resolved HTTP 403 Access Denied errors affecting JavaScript and CSS assets. 
Implemented an S3 bucket policy to allow public read access to website resources. 
Successfully published a functional public website accessible via the internet. 
