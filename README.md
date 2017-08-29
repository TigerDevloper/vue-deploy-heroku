# vue-deploy-heroku
Necessary files for deploying Vue.js app built by vue-cli on Heroku.
## Installation
1.) Build the vuejs project
```bash
yarn build
# ./dist directory will appear after finished
```
2.) Remove dist/ in `.gitignore`

3.) Add dist to git and commit changes
```bash
git add dist
git commit -am "Add dist directory"
```


4.) Copy `package.json` and `server.js` into *dist* folder.

5.) Add `deploy` script to your ***root*** `package.json` file:
```json
"scripts": {
  "deploy": "npm run build && git subtree push --prefix dist heroku master"
}
```
6.) If you haven't set up Heroku remote repository, run:
```bash
heroku apps:create <app_name>
```
7.) Once your remote heroku repository is ready, run:
```bash
yarn deploy
```
## Usage
When you want to deploy your app to Heroku, run:
```bash
# build and deploy to Heroku
yarn deploy
```
