# github-blueteam
Notes on GitHub incident response, forensics, and log analysis.

## Non-MFA Authentication
Ways to authenticate to GitHub users and orgs without 2fa.

### OAuth Apps - Org
There is a policy orgs can set regarding outside apps being installed (given access to) said org.  

Bypasses third-party Oauth App restrictions if owned by the same org.  

For example, if I make a personal GitHub App called "Bronco", and the org I want to install it to requires approval, "Bronco" will show as pending approval when attempting to install it.
However if I make an org GitHub App called "Mustang", and the org I want to install it to is the same one that owns it, "Mustang" will not require approval when installing (please cite).
There is a third case of GitHub-official applications referred to as `Internal OAuth Apps`.

### GitHub Apps - Personal
Org

### GitHub Apps - Org
Same as personal, but owned by an organization.

### Personal Access Tokens - Fine Grained
Personally creatable, Org restrictable, can require org admin per-token approval, active tokens for an organization can be tracked.

```
Restrict access via fine-grained personal access tokens

By default, fine-grained personal access tokens cannot access content owned by your organization via the Public API or Git. This includes both public and private resources such as repositories.
Allow access via fine-grained personal access tokens

API and Git access will be allowed using approved organization member's fine-grained personal access tokens
Restrict access via fine-grained personal access tokens

Organization members will not be allowed to access your organization using a fine-grained personal access token
```

### Personal Access Tokens - Classic
Personally creatable, Org restrictable, Person can self-authorize for an org (still requires a setting, as strict as it gets, cannot require per-token admin approval)

```
By authorizing, owners of Sentry will be able to see this personal access token’s access scopes and when it was last used. 
```


## References
(Limiting OAuth app and GitHub App access requests)[https://docs.github.com/en/organizations/managing-programmatic-access-to-your-organization/limiting-oauth-app-and-github-app-access-requests]

