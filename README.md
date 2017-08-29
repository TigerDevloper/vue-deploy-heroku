# vue-deploy-heroku
Necessary files for deploying Vue.js app built by vue-cli on Heroku.
## Installation
```bash
# Inside vue project
yarn build
cd dist
git clone --depth=1 https://github.com/kykungz/vue-deploy-heroku.git
```
## Usage
If you haven't set up Heroku remote repository, run:
```bash
heroku apps:create <app_name>
```
Add `deploy` script to your *root* `package.json` file:
```json
"scripts": {
  "deploy": "git subtree push --prefix dist heroku master"
}
```

Once your remote heroku repository is ready. Run:
```bash
yarn deploy
```
