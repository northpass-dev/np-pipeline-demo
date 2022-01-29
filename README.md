# np-pipeline-demo
This contains sample templates to demonstrate how to build a CI/CD pipeline with Northpass using Github Actions. Visit the [Northpass Developer Hub](https://developers.northpass.com/docs/templates-overview) to learn more about templates and how they can be used to customize your academy.

## Configure API Key Secret
Your Northpass Academy API key is required to push templates programmatically to your academy. We will be using a GitHub repository secret in order to keep your API key safe and still be able to reference it within the GitHub action.

For the sake of this demo, we will create a secret called:

```
NORTHPASS_API_KEY
```

Visit GitHub's documentation on [how to create an encrypted secret for a repository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).
