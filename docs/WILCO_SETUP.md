# WILCO_ENGINE_URL Configuration Guide

This guide provides detailed information about configuring the `WILCO_ENGINE_URL` secret for the Anythink Market repository.

## Overview

The `WILCO_ENGINE_URL` secret is used by the GitHub Actions workflow to connect to the Wilco engine for automated checks on pull requests.

## Setting Up the Secret

### Method 1: GitHub Web Interface

1. Navigate to your repository on GitHub
2. Go to **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Enter the following details:
   - **Name**: `WILCO_ENGINE_URL`
   - **Value**: Your Wilco engine endpoint URL (e.g., `https://engine.example.com/api/v1`)
5. Click **"Add secret"**

### Method 2: GitHub CLI

```bash
gh secret set WILCO_ENGINE_URL --body "https://your-wilco-engine-url.com/api/v1"
```

## URL Format Requirements

- Must be a valid HTTP or HTTPS URL
- Should start with `http://` or `https://`
- Recommended to use HTTPS for security
- Should point to a valid Wilco engine endpoint

## Workflow Behavior

### When Secret is Configured
- ✅ The workflow validates the URL format
- ✅ Runs the Wilco checks using the provided endpoint
- ✅ Continues with normal PR validation

### When Secret is Missing
- ⚠️ Displays a warning message with setup instructions
- ⚠️ Skips the Wilco checks
- ✅ Workflow still passes (non-blocking)

## Troubleshooting

### Secret Not Working
1. **Check the secret name**: Must be exactly `WILCO_ENGINE_URL` (case-sensitive)
2. **Verify URL format**: Should start with `http://` or `https://`
3. **Test endpoint**: Ensure the Wilco engine is accessible
4. **Repository permissions**: You need admin/write access to set secrets

### Workflow Failures
1. **Check workflow logs**: Look for error messages in the Actions tab
2. **Validate URL**: Ensure your Wilco engine endpoint is responding
3. **Network issues**: Check if there are any firewall or network restrictions

### Getting Help
- Check the workflow logs in the Actions tab of your repository
- Review the error messages displayed in the workflow output
- Ensure your Wilco engine endpoint is configured correctly

## Security Notes

- Secrets are encrypted and not visible in logs
- Only repository collaborators with appropriate permissions can set secrets
- The URL validation step shows only the first 20 characters for security
- Use HTTPS URLs when possible for secure communication