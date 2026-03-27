# Diffian Website

Static landing page, deployed to AWS S3 + CloudFront via GitHub Actions.

---

## Stack

| Layer | Service |
|---|---|
| Hosting | AWS S3 (static) |
| CDN | AWS CloudFront |
| CI/CD | GitHub Actions (OIDC — no long-lived keys) |
| IaC | AWS CloudFormation (`infrastructure/cloudformation.yml`) |

---

## One-time setup

### 1. Create the GitHub organization

GitHub organizations cannot be created via CLI. Go to:

> https://github.com/organizations/plan

Create the **diffian** org (or **diffian-dev** / **diffian-io** if taken), then transfer this repo into it:

> Repo Settings → Danger Zone → Transfer repository → `diffian/diffian-website`

Once transferred, update the OIDC condition in `infrastructure/cloudformation.yml`:

```yaml
token.actions.githubusercontent.com:sub: 'repo:diffian/diffian-website:*'
```

Then re-deploy the CloudFormation stack to pick up the change.

---

### 2. Deploy the AWS infrastructure

Requires AWS CLI configured for the **cloudavian** account.

```bash
# Check whether the GitHub OIDC provider already exists in your account
aws iam list-open-id-connect-providers

# If it doesn't exist, uncomment the GitHubOIDCProvider resource in the template first.

aws cloudformation deploy \
  --stack-name diffian-website \
  --template-file infrastructure/cloudformation.yml \
  --capabilities CAPABILITY_NAMED_IAM \
  --region us-east-1
```

CloudFront distributions must be created in **us-east-1** (global service). The S3 bucket will also be created there.

---

### 3. Retrieve stack outputs

```bash
aws cloudformation describe-stacks \
  --stack-name diffian-website \
  --query 'Stacks[0].Outputs' \
  --output table \
  --region us-east-1
```

Note down:
- `BucketName`
- `DistributionId`
- `GitHubActionsRoleArn`

---

### 4. Add GitHub Actions secrets

In the repo (or org) secrets — **Settings → Secrets and variables → Actions**:

| Secret name | Value |
|---|---|
| `AWS_ROLE_ARN` | `GitHubActionsRoleArn` output from CloudFormation |
| `AWS_REGION` | `us-east-1` |
| `AWS_S3_BUCKET` | `BucketName` output from CloudFormation |
| `AWS_CLOUDFRONT_DISTRIBUTION_ID` | `DistributionId` output from CloudFormation |

---

### 5. Push to trigger first deploy

```bash
git push origin main
```

The GitHub Actions workflow (`.github/workflows/deploy.yml`) will:

1. Authenticate to AWS via OIDC (no stored credentials)
2. Sync all website files to S3, deleting removed files
3. Set `index.html` to a short cache TTL (60s browser / 1h CloudFront)
4. Invalidate the CloudFront cache so changes go live immediately

---

## Custom domain (optional)

1. Request an ACM certificate in **us-east-1** for your domain
2. Add the certificate ARN to `AlternateDomains` + `ViewerCertificate` in `infrastructure/cloudformation.yml`
3. Re-deploy the stack
4. Point your DNS CNAME (or ALIAS for apex) to the `DistributionDomain` output

---

## Local development

The site is a single static HTML file — just open `index.html` in a browser:

```bash
open index.html
# or
python3 -m http.server 8080
```
