# np-pipeline-demo
This contains sample templates to demonstrate how to build a CI/CD pipeline with Northpass using Github Actions. Visit the [Northpass Developer Hub](https://developers.northpass.com/docs/templates-overview) to learn more about templates and how they can be used to customize your academy.

## Configure API Key Secret
Your Northpass Academy API key is required to push templates programmatically to your academy. We will be using a GitHub repository secret in order to keep your API key safe and still be able to reference it within the GitHub action.

For the sake of this demo, we will create a secret called:

```
NORTHPASS_API_KEY
```

Visit GitHub's documentation on [how to create an encrypted secret for a repository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).

## Breaking Down the Workflow

The workflow is defined in the [northpass-pipeline-demo.yml](https://github.com/northpass-dev/np-pipeline-demo/blob/main/.github/workflows/northpass-pipeline-demo.yml) file. We currently have the Action set to run every time new code is pushed, but you can change this to your liking.

As you can see from the definition, we have dependencies on a few things:

1. You must checkout the repository so that we can access the files
2. `node` must be installed

To make things easier, we've created an npm package, [np-template-uploader](https://www.npmjs.com/package/np-template-uploader), that will orchestrate the file movement. The package is a binary that takes two command line arguments:

* Your Northpass Academy API Key
* The path of the folder containing your templates

### Important Points

This will synchronize your templates to your academy. This means that any templates removed from your repository will also be removed from your academy.

Additionally, the template uploader does not search recursively through folders just yet. We'll be sure to add that soon.