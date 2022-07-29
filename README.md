# Events 7 dashboard - Vue 3 & Firebase (Cloud Firestore)
Internal web tool “Events7” (dashboard), designed for the Analytics team to define client events
we want to track. For example if we want to track button clicks in our mobile app, the Analytics 
team would go on the dashboard and define the event. The event definition consists of
unique id, name, description, type (crosspromo, liveops, app, ads), priority (from 0-10) and 
related events.
The Analytics team can view, create, edit and delete event definitions.

## Prerequisites
You will need [Node.js](https://nodejs.org/en/) version 6.0 or greater installed on your system.
                                                                                  
## Instructions on how to build this project from scratch
The application is make with [Vue CLI](https://cli.vuejs.org/), which is a standard tooling for Vue.js development.
### Project setup
```
  npm install -g @vue/cli
  #OR
  yarn global add @vue/cli
```
```
  vue create events7
  cd events7 
  npm install
  npm run dev
```
#### NOTE: The charts are created using the Chart.js library.

### Firebase: Project Setup
For detailed information see [Cloud Firestore](https://firebase.google.com/docs/firestore).
* First a firebase project should be created
* Then the firebase project should be connected to our app. To do that we create a web project
(this can be found on the firebase dashboard page) and follow the instructions. 
  * Make sure to install firebase in your web application
  ```
    npm install firebase
  ```
* Then create the database.
  * NOTE: In this project, the database is created in test mode.
 
## Project deployment to GitHub pages
Before you get started, create a github repository.
* In your application create a file named "vue.config.js" and add the following code:
```
  module.exports = {
    publicPath: '/github-repository-name/'
  }
```
* Then create a shell script "deploy.sh", and add the following code: 
```
  #!/usr/bin/env sh

  # abort on errors
  set -e

  # build
  npm run build

  # navigate into the build output directory
  cd dist

  # if you are deploying to a custom domain
  # echo 'www.example.com' > CNAME

  git init
  git add -A
  git commit -m 'deploy'

  # if you are deploying to https://<USERNAME>.github.io
  # git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git main

  # if you are deploying to https://<USERNAME>.github.io/<REPO>
  # git push -f git@github.com:<USERNAME>/<REPO>.git main:gh-pages

  cd -
```
* Next you should set execution permition for that script
  * Linux:
  ```
    chmod +x deploy.sh
  ```
  * Windows: 
  ```
    attrib +x deploy.sh
  ```
 * In order to be able to run this script, a ssh key should be created. Example:
 ```
  ssh-keygen -t ed25519 -C "your-github-email"
  cat /path-to-your-key/
 ```
 * Insert the key code in github > settings > SSH and GPG keys > new SSH key
 * Then, in package.json file add new script:
 ```
  "deploy": "deploy.sh sh"
 ```
 #### Build the project for production:
 ```
 npm run deploy
 ```

## Instructions on how to run the project from the github repository.
Get the code by either cloning this repository using git:
```
  https://github.com/teodora-taleska/vue-dashboard-app.git
```
... or by downloading the source code as a zip archive.

#### Once downloaded, open the terminal in the project directory, and continue with:
```
  npm install
```
#### Compiles and hot-reloads for development
```
  npm run serve
```
#### Compiles and minifies for production
```
  npm run build
```


### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

