Creately Mobile App Test 1
================
###(Codename: Electron)###
This is the sourcecode of the Creately Mobile hybrid app. The app is focused on letting mobile users viewing and collaborating on diagrams. Full specification can be found on [Google Sites](https://sites.google.com/a/cinergix.com/creately-player-viewer-and-mobile/functional-sepcifications/2-5-creately-mobile).

# Setting Up #
This section discusses setting up the development enviornment for the Electron project. 

Download and install

* [NodeJS](https://nodejs.org/en/download/)
* [Ruby](http://rubyinstaller.org/downloads/) ( Only if needed in 4th step )

Run the following commands in cmd / terminal. ( If you get 'Permission denied' error in OS X or Linux follow [ steps  here](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md) )

###### 1. Install Yeoman tools
 ```sh
 npm install -g yo bower grunt-cli
 ```
###### 2.  Install cordova
```sh
npm install -g cordova
```
###### 3. Install ionic
```sh
npm install -g ionic
```
###### 4. Install Sass 
Ruby will be required. In case of command not recognized issue, run the command in 'Start Command prompt with Ruby' or [see here](./README.md#user-content-windows---command-not-recognized-issue)
```sh
gem install compass
```
###### 5. Install typescript compiler
```sh
npm install -g typescript
```
###### 6. Install DefinitelyTyped for typescript support on javascript libraries
```sh
npm install -g tsd
```
###### 7. Clone the Electron project 
In case of command not recognized issue, run the command in 'Git Bash' or [see here](./README.md#user-content-windows---command-not-recognized-issue)
```sh
git clone https://github.com/Cinergix/electron/ 
```
###### 8. Navigate to the project path 'electron'
```sh
cd electron
```
###### 9. Update NPM packages
```sh
npm install
```
###### 10. Lists front-end dependencies thorugh Bower
```sh
bower install
```
###### 11. Typescript definitions installed from DefinitelyTyped
```sh
tsd install
```

#####Windows - Command not recognized issue 

If you get following error in cmd,

`{your_command} is not recognized as an internal or external command`

Make sure that you have correctly set PATH (under Environment Variables in Windows) to point at {your_command} installation bin path.

e.g.

If `gem install compass` results `gem is not recognized as an internal or external command`
, append ruby installation path ( C:\Ruby22\bin; ) to PATH variable.

If `git clone https://github.com/Cinergix/electron/` results `git is not recognized as an internal or external command`
, append git installation path ( C:\Program Files (x86)\Git\bin; ) to PATH variable.


# Running, Testing and Building #
This section discusses all the commands that can be used in this project. This uses Grunt and all the configuration can be found in Gruntfile.js.

* `grunt serve` - This can be used to run the app through a nodejs server and lauch on the current browser. Best for developing and debugging. This will watch file changes and relaod the app.
* `grunt test` - This will run the karma tests and must be used when writing spec and code. This will watch file changes and re-run the tests. However config changes may require you to re-run the command.
* `grunt coverage` - This will run the test coverage report. Provides full report on the unit test coverage
* `grunt emulate:ios` - This will run the app on the iOS emulator. Requires to be installed along with XCode.
* `grunt emulate:android` - This will run the app on the android emulator. Requires the android SDK to be installed. 

For more details on the available functionality on this generator [see this project](https://github.com/diegonetto/generator-ionic/blob/master/README.md).

# Project Structure #

    ├── Gruntfile.js            - Configuration of all Grunt tasks and workflow
    ├── package.json            - NPM Dev dependencies and required Cordova plugins
    ├── bower.json              - Lists front-end dependencies thorugh Bower
    ├── tsd.json                - Typescript definitions installed from DefinitelyTyped 
    ├── config.xml              - Global Cordova configuration
    ├── ionic.project           - Ionic project configuration
    ├── .gitignore              - Resources and files that do not require to be checked into git
    ├── .bowerrc                - Bower configuration
    ├── .editorconfig           - General editor configuration supported by many editors (editorconfig.org)
    ├── .jshintrc               - Jshint configuration for project
    ├── .jshintignore           - Jshint ignore files/patterns
    ├── app/                    - Source of the application. This is where most of the editing happens.
    │   ├── index.html          - Main Ionic app entry point html file
    │   ├── lib/                - Libraries managed by Bower (gitignored)
    │   ├── scripts/            - All typescript source files (Essentially the sourcecode)
    │   ├── test/               - All typescript test files
    │   │   ├── spec/           - Unit tests. shares the same structure as the scripts folder.
    │   │   ├── mock/           - Mock files for the tests
    │   ├── styles/             - Stylesheets and Scss files
    │   ├── fonts/              - Fonts used by the app
    │   ├── images/             - Images used by the app
    │   ├── templates/          - HTML views and templates (would share similar structure as scripts)
    │   ├── typings/            - Definitions downloaded by tsd (gitignored)
    ├── resources/              - Project icons and splash screens for each platform
    │   ├── ios/
    │   ├── android/
    ├── platforms/              - Targeted operating systems (gitignored)
    ├── plugins/                - Native plugins (gitignored)
    ├── hooks/                  - Cordova lifecycle hooks
    ├── test/                   - All javascript tests that were compiled (gitignored)
    │   ├── coverage/           - Istanbul generated test reports
    │   ├── spec/
    │   ├── mock/
    ├── www/                    - The distribution folder that contains compiled and prepared files from app folder (gitignored)
