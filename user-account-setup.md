# User account setup

## Create a GitHub account and set up your profile

To contribute to the docs.microsoft.com technical content, you'll need a [GitHub](https://www.github.com) account. Go to [https://www.github.com](https://www.github.com) and select *Sign up for GitHub*.

## Permissions in GitHub

Anyone with a GitHub account can contribute to docs.microsoft.com content through one of the [public repositories][DocsPubRepos]. No additional permissions are required for public repositories.

## Create an access token

See [Creating an access token for command-line use](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) to create a security token that will be used for authentication when accessing GitHub from command line functions. When you create the token, select all the scopes available in the token-creation UI ([details on each scope](https://developer.github.com/v3/oauth/#scopes))

The access token will be used instead of your GitHub password, whenever you need to access a GitHub repository from the command line. It's a long string that looks something like this:  fdd3b7d3d4f0d2bb2cd3d58dba54bd6bafcd8dee. When you create your access token, **save it in a text file in a safe location** to make it readily accessible when you need it.

## Next steps
- [Tools setup](./tools-setup.md) 
- Back to [contributors guide](./readme.md)

<!--Anchors-->

[DocsPubRepos]: ./repository-organization.md