# vue-deploy-heroku
Necessary files for deploying Vue.js app built by vue-cli on Heroku.<br>***Only tested on `webpack` template.***
## Create Heroku Repository
If you haven't set up Heroku remote repository, run:
```bash
heroku apps:create <app_name>
```
## Installation
1.) Copy *dist* folder into your application directory so that your project's looks like:
```
my-vue-project
 ├── .git/
 ├── build/
 ├── config/
 ├── dist/             #
 │   ├── package.json  #
 │   └── server.js     #
 ├── node_modules/
 ├── src/
 .
 .
 ├── .gitignore
 ├── package.json
 .
 .
 .
```

2.) Remove dist/ in `.gitignore`
```
.DS_Store
node_modules/

dist/ <<<< REMOVE THIS

npm-debug.log*
yarn-debug.log*
```

3.) Add `deploy` script to your ***root*** `package.json` file:
```json
"scripts": {
  "deploy": "git subtree push --prefix dist heroku master"
}
```
## Usage
```bash
# build vuejs files
yarn build

# add to git
git add -A
git commit -am "Add build files"

# deploy to heroku
yarn deploy
```
