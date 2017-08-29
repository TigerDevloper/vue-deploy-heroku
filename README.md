# vue-deploy-heroku
Necessary files for deploying Vue.js app built by vue-cli on Heroku.
## Usage
1.) Build the vuejs project
```bash
yarn build
```
2.) Copy `package.json` and `server.js` into *dist* folder.

3.) Add `deploy` script to your ***root*** `package.json` file:
```json
"scripts": {
  "deploy": "git subtree push --prefix dist heroku master"
}
```
4.) If you haven't set up Heroku remote repository, run:
```bash
heroku apps:create <app_name>
```
5.) Once your remote heroku repository is ready, run:
```bash
yarn deploy
```
