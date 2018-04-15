# Deploy your App to GitHub Pages

To deploy our changes to GitHub pages we will use the `angular-cli-ghpages` package: <https://github.com/angular-buch/angular-cli-ghpages>

* You need to have a GitHub user account.
* You need to create a repository for your project.
* You need to commit all the changes you made in the project.
* You need to install `angular-cli-ghpages`.

## Creating a GitHub account

(If you already have a GitHub account you can skip this step.)

To create a GitHub user go to GitHub: <https://github.com/>

Complete the registration form and make sure to validate your email address.

## Creating your App repository

After logging in to GitHub, click on the `Start a project` button, and name the repository `ng-girls-todo` (or any other name you like).

## Connecting your repository

Commit all your changes by running these commands in your project directory:

```
git add -A
git commit -m "Your Message"
```

Run the following commands to connect your code to your repository.
Make sure to replace `{YOUR_USERNAME}`, `{YOUR_REPO}`, etc., with your GitHub username, repository name, etc.

```
git remote add origin https://github.com/{YOUR_USERNAME}/{YOUR_REPO}.git
git push -u origin master
```

## Deploying to GitHub Pages

First install `angular-cli-ghpages`:

```
npm i -g angular-cli-ghpages
```

Then run these commands:

```
ng build --prod --base-href="/{YOUR_REPO}/"
angular-cli-ghpages
```

Your app will be available at <https://{YOUR_USERNAME}.github.io/{YOUR_REPO}>.

For more information, see <https://github.com/angular-schule/angular-cli-ghpages>.

## Known Issues

On Windows machines, you may run into an issue like the following:

```
An error occurred!
 Error: Unspecified error (run without silent option for detail)
    at C:\Users\<myuser>\AppData\Roaming\nvm\v8.9.1\node_modules\angular-cli-ghpages\node_modules\gh-pages\lib\index.js:232:19
    at _rejected (C:\Users\<myuser>\AppData\Roaming\nvm\v8.9.1\node_modules\angular-cli-ghpages\node_modules\q\q.js:844:24)
    ...
```

Try to debug it with `angular-cli-ghpages -S`. If you get the following error:

```
fatal: could not read Username for \'https://github.com\': No error\n',
```

You can do the following:

1. Create a Personal Access Token here: <https://github.com/settings/tokens>

2. Run the following command with your token, username, repository, displayed username, and email address:

```
angular-cli-ghpages --repo=https://{YOUR_PERSONAL_ACCESS_TOKEN}@github.com/{YOUR_USERNAME}/{YOUR_REPO}.git --name="Displayed Username" --email={YOUR_EMAIL_ADDRESS}
```

