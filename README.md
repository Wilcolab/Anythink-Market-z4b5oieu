# Anythink Market

This repository includes GitHub Actions workflows that require certain secrets to be configured.

## Required Secrets

### WILCO_ENGINE_URL

The Wilco engine URL is required for the automated checks to run properly. 

**To set this secret:**

1. Go to your repository's Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Name: `WILCO_ENGINE_URL`
4. Value: Your Wilco engine endpoint URL

**Or use the GitHub CLI:**

```bash
gh secret set WILCO_ENGINE_URL --body "<your-wilco-engine-url>"
```

**Note:** Without this secret configured, the Wilco checks will be skipped in pull requests, but the workflow will still pass.

## Workflow Status

The GitHub Actions workflow will:
- ✅ Run successfully when `WILCO_ENGINE_URL` is configured
- ⚠️ Skip Wilco checks (with warning) when `WILCO_ENGINE_URL` is not configured
- Display clear instructions on how to fix the configuration