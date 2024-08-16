# action-platformsh-url

Detecting if PlatformSH is building an environment, and returning the
URL when it's done deploying.

## Inputs

- `PLATFORMSH_ID`: The ID of your platform project.
- `PLATFORMSH_KEY`: The API token, generated through PlatformSH.
  - Login to [console.platform.sh](https://console.platform.sh)
  - "My Profile" > "API Tokens" > "Create API token"
  - Remember that this is an access token, and **should not be written
    in plain text.**
  - Add it as an encrypted repo secret - [more info at GitHub
    docs](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).
- `ENVIRONMENT_NAME` (optional): The environment, to check for
  - By default, this is set to the `pr-xx`, using `pr-${{
    github.event.pull_request.number }}`
  - You can also set it to check for the current branch, using `${{
    github.head_ref || github.ref_name }}`

See the other inputs in [action.yml](action.yml)

## See also

This action is used for another action, for detecting if a platformsh
environment has deployed correctly.

<https://github.com/rasben/action-platformsh-deploy-status>
