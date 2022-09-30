# action-platformsh-url

Detecting if PlatformSH is building an environment, and returning the URL when it's done deploying.

## Inputs

- `PLATFORMSH_ID`: The ID of your platform project
- `ENVIRONMENT_NAME` (optional): The environment, to check for
	- By default, this is set to the `pr-xx`, using `pr-${{ github.event.pull_request.number }}`
	- You can also set it to check for the current branch, using `${{ github.head_ref || github.ref_name }}`

## Secrets

- `PLATFORMSH_KEY`: Your Platform.SH token.
	- Login to [console.platform.sh](https://console.platform.sh)
	- "My Profile" > "API Tokens" > "Create API token"

## Using the action

Example setup: https://github.com/reload/workflow-platformsh-deploy-status/blob/main/.github/workflows/platformsh-deploy-test.yml
