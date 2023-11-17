# prerender-io-cloudfront-s3
Optimize SEO for JavaScript websites with Prerender.io. Server-side pre-rendering enhances search engine visibility, accelerates page loads, and ensures accurate social media previews. Compatible with popular frameworks. Elevate your website's SEO performance today!


## Prerender.io AWS Infrastructure

This repository encompasses AWS CloudFormation templates designed for the implementation of Prerender.io, aiming to improve SEO and enhance the performance of JavaScript-driven websites. It comprises two distinct components:

### 1. CloudFormation Setup:
The first part provides a comprehensive CloudFormation example. It covers the entire process, starting from configuring an S3 bucket for static website hosting to establishing a CloudFront distribution for the same. Additionally, it includes the setup of a Lambda@Edge function, contributing to the complete Prerender.io integration within the AWS environment.

[Link to CloudFormation](./cloudformation-stack-example/README.md)

### 2. Manual Configuration Steps:
The second part guides users through manual steps. In scenarios where a website is served from an S3 bucket using CloudFront, this section explains how to manually configure the Prerender.io middleware. This manual setup enables users to transform their web pages into fully rendered HTML content when a web crawler, such as a bot, traverses any URL on the website.

[Link to Manual Setup](./manual-setup/README.md)

In essence, this repository provides both an automated CloudFormation approach and a step-by-step guide for users who prefer manual configuration, ensuring flexibility in implementing Prerender.io based on individual preferences and requirements.