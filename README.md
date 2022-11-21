# action-platformsh-url

Detecting if PlatformSH is building an environment, and returning the URL when it's done deploying.

## Inputs

- `PLATFORMSH_ID`: The ID of your platform project
- `ENVIRONMENT_NAME` (optional): The environment, to check for
	- By default, this is set to the `pr-xx`, using `pr-${{ github.event.pull_request.number }}`
	- You can also set it to check for the current branch, using `${{ github.head_ref || github.ref_name }}`

## Secrets
These are inputs that you should treat as secrets.
You use them the same way as the other inputs, but instead of writing the data directly in the `yml`, you should use Github secret environments.

It could look something like this:

```yml
        with:
          PLATFORMSH_KEY: ${{ secrets.PLATFORMSH_KEY }}
```

More info here:

https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository


- `PLATFORMSH_KEY`: Your Platform.SH token.
	- Login to [console.platform.sh](https://console.platform.sh)
	- "My Profile" > "API Tokens" > "Create API token"
