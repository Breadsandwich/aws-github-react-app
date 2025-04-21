# React App with AWS S3 and CloudFront Deployment

This is a React application template that includes automated deployment to AWS S3 and CloudFront using GitHub Actions.

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- AWS Account
- GitHub Account

## Local Development

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm start
```

The app will be available at `http://localhost:3000`

## AWS Setup

Before deploying, you'll need to set up the following in AWS:

1. Create an S3 bucket for hosting your static website
2. Create a CloudFront distribution pointing to your S3 bucket
3. Create an IAM user with appropriate permissions for GitHub Actions

### S3 Bucket Setup

1. Create a new S3 bucket with the following settings:
   - Enable static website hosting
   - Set bucket policy to allow public access
   - Configure CORS if needed

### CloudFront Setup

1. Create a new CloudFront distribution:
   - Set the origin to your S3 bucket
   - Configure SSL certificate
   - Set up caching behavior

### IAM User Setup

1. Create a new IAM user with programmatic access
2. Attach the following policies:
   - AmazonS3FullAccess
   - CloudFrontFullAccess

## GitHub Actions Setup

1. Add the following secrets to your GitHub repository:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_REGION`
   - `S3_BUCKET_NAME`
   - `CLOUDFRONT_DISTRIBUTION_ID`

## Deployment

The application is automatically deployed to AWS S3 and CloudFront when changes are pushed to the main branch. The deployment process:

1. Builds the React application
2. Uploads the build files to S3
3. Invalidates the CloudFront cache

## Project Structure

```
├── src/                # Source files
├── public/            # Static files
├── .github/           # GitHub Actions workflows
└── package.json       # Project dependencies
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License.
