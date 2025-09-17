# Setting Up WILCO_ENGINE_URL Secret

## Problem
The GitHub Actions workflow is failing with a "context access might be invalid" error for `WILCO_ENGINE_URL` because this required secret is not configured in the repository settings.

## Solution
Follow these steps to configure the required secret:

### Step 1: Navigate to Repository Settings
1. Go to your repository on GitHub: https://github.com/Wilcolab/Anythink-Market-z4b5oieu
2. Click on the **Settings** tab (you need admin access to the repository)

### Step 2: Access Secrets Configuration
1. In the left sidebar, click on **Secrets and variables**
2. Click on **Actions** from the dropdown

### Step 3: Add the Secret
1. Click the **New repository secret** button
2. In the **Name** field, enter: `WILCO_ENGINE_URL`
3. In the **Value** field, enter your Wilco engine endpoint URL
   - Contact your Wilco administrator for the correct endpoint URL
   - The URL should follow the format: `https://your-wilco-engine.domain.com`
4. Click **Add secret**

### Step 4: Verify Configuration
After adding the secret:
1. The secret should appear in your repository secrets list
2. Re-run any failed GitHub Actions workflows
3. The workflow should now access the Wilco engine successfully

## Troubleshooting
- **No access to Settings**: Ensure you have admin or maintainer permissions on the repository
- **Workflow still failing**: Verify the WILCO_ENGINE_URL value is correct and accessible
- **Secret not appearing**: Make sure you're in the correct repository and the secret name is exactly `WILCO_ENGINE_URL`

## Security Notes
- Repository secrets are encrypted and only accessible to GitHub Actions workflows
- The secret value will not be visible after creation
- Only repository administrators can view and modify secrets