# Anythink Market

This repository uses Wilco for automated PR checks and code analysis.

## Setup Requirements

### GitHub Actions Configuration

This repository requires the `WILCO_ENGINE_URL` secret to be configured for the GitHub Actions workflow to function properly.

**If you see errors like "WILCO_ENGINE_URL context might be invalid":**

1. **Repository administrators** need to set up the required secret
2. Follow the detailed instructions in [SETUP_WILCO_SECRET.md](./SETUP_WILCO_SECRET.md)
3. Quick setup: Go to **Settings** → **Secrets and variables** → **Actions** → **New repository secret**
   - Name: `WILCO_ENGINE_URL`
   - Value: Your Wilco engine endpoint URL

### Workflow Status

The GitHub Actions workflow will automatically:
- ✅ Check if the WILCO_ENGINE_URL secret is properly configured
- 🔄 Run Wilco PR checks when the secret is available
- ❌ Fail with clear instructions if the secret is missing

## Contributing

When contributing to this repository:
1. Ensure your changes pass the Wilco checks
2. If workflows fail due to missing secrets, contact a repository administrator
3. Follow the existing code style and patterns

## Support

- For Wilco setup issues: See [SETUP_WILCO_SECRET.md](./SETUP_WILCO_SECRET.md)
- For general questions: Create an issue in this repository