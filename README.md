# heroku-create-npmrc-buildpack
Create a .npmrc file in the build directory which allows you to install private packages from a private GitHub Package Repository.

This buildpack should be **run before the buildpack `heroku/nodejs`**.

You must set the following config variables:

```
heroku config:add GITHUB_COMPANY @my_company_name
heroku config:add GITHUB_NPM_AUTH_TOKEN my_auth_token
```

Where:
- `@my_company_name` the name of the owner of the GitHub repository preceded by an `@`, e.g. @orderstatistics.
- `my_auth_token` is a personal access token with (at a minimum) read:package rights. To create a token head over to GitHub: https://github.com/settings/tokens.