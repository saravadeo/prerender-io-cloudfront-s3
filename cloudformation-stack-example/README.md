# prerender-io-cloudfront-s3
Optimize SEO for JavaScript websites with Prerender.io. Server-side pre-rendering enhances search engine visibility, accelerates page loads, and ensures accurate social media previews. Compatible with popular frameworks. Elevate your website's SEO performance today!


## Prerender.io AWS Infrastructure

This repository contains AWS CloudFormation templates to set up Prerender.io for enhancing SEO and optimizing the performance of JavaScript-driven websites.

### Prerequisites

- AWS account
- AWS CLI installed and configured
- Git installed

### Steps to Deploy

**Clone the Repository:**

   ```bash
   git clone https://github.com/saravadeo/prerender-io-cloudfront-s3.git
   cd your-repo
   ```

### Deploying the CloudFormation Stack

```bash
aws cloudformation deploy --stack-name PrerenderStack --template-file template.yaml --parameter-overrides PrerenderToken=your-token
```

### Wait for Deployment to Complete:

Monitor the CloudFormation stack creation progress in the AWS Management Console or use the following CLI command:

```bash
aws cloudformation describe-stacks --stack-name PrerenderStack --query "Stacks[0].StackStatus"
```

### Accessing Resources:

Once the stack is created, navigate to the AWS Management Console to view the S3 bucket (WebBucket), Lambda functions (SetPrerenderHeader and RedirectToPrerender), and CloudFront distribution (CloudFront).

### Uploading Files to S3 Bucket

- Upload code.js and index.html to the S3 bucket created by CloudFormation in step 1.
- Change the read permissions for code.js and index.html to be publicly readable.

### Testing
To view the page as rendered by prerender.io, use the following command:

```bash
curl -H 'User-Agent: Facebot' https://${CLOUDFRONT_DOMAIN}/over/here
```

To view the same page without pre-rendering, use:
```bash
curl https://${CLOUDFRONT_DOMAIN}/over/here
```

Make sure to replace ${CLOUDFRONT_DOMAIN} with the actual CloudFront domain.

### Clean Up (Optional):

If needed, you can delete the stack using:

```bash
aws cloudformation delete-stack --stack-name PrerenderStack
```

## Notes

- Ensure your AWS CLI is configured with the necessary permissions.
- Make sure to invalidate the CloudFront cache after each deployment to reflect changes.
- Customize Lambda function code as needed for specific requirements.

Feel free to contribute or report issues! Happy optimizing! 🚀
