# Anythink Market

This repository includes GitHub Actions workflows that require certain secrets to be configured.

## Required Secrets

### WILCO_ENGINE_URL

The Wilco engine URL is required for the automated checks to run properly. 

**For detailed setup instructions, see [docs/WILCO_SETUP.md](docs/WILCO_SETUP.md)**

**To set this secret:**

1. Go to your repository's Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Name: `WILCO_ENGINE_URL`
4. Value: Your Wilco engine endpoint URL (should be a valid HTTPS URL)

**Or use the GitHub CLI:**

```bash
gh secret set WILCO_ENGINE_URL --body "<your-wilco-engine-url>"
```

**Example URL format:**
```
https://engine.example.com/api/v1
```

**Note:** Without this secret configured, the Wilco checks will be skipped in pull requests, but the workflow will still pass.

## Workflow Status

The GitHub Actions workflow will:
- ✅ Run successfully when `WILCO_ENGINE_URL` is configured
- ⚠️ Skip Wilco checks (with warning) when `WILCO_ENGINE_URL` is not configured
- Display clear instructions on how to fix the configuration

## Troubleshooting

### Common Issues

**1. Secret not being recognized**
- Ensure the secret name is exactly `WILCO_ENGINE_URL` (case-sensitive)
- Verify you're setting it as a repository secret, not an environment secret

**2. Workflow still failing**
- Check that your Wilco engine URL is accessible
- Ensure the URL uses HTTPS protocol
- Verify the endpoint is correct and responding

**3. Permission issues**
- Ensure you have admin or write access to the repository to set secrets
- Check that GitHub Actions are enabled for your repository