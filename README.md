# Linting

Linting is the process of running a code (called lint) on a codebase that will flag programming errors, bugs, stylistic errors and suspicious constructs. 
There are differents lints to choose from depending on the programming langauge used in the codebase. 

## ReactJS and JavaScript
For React and JavaScript, ESLint is used. Here is how to set it up: 

### Intalling ESLint
There are 2 ways to install ESLint, either gloablly or in a specific project.  

**Gloablly**

Type: 

```
npm install eslint -g
```
**In a Specific Project**

In the project directory, type: 
```
npm install eslint --save-dev
```
### Initializing ESLint
For Mac: 
```
npx eslint --init
```
For Windows: 
```
cd node_modules/.bin
eslint --init
```
After typing the above, you will asked a series of questions. You can follow the below template or choose your own preferences. 

- **How would you like to use ESLint?** To check syntax, find problems and enforce code style
- **What type of modules does your project use?** JavaScript modules (import/export) 
- **Which framework does your project use?** React
- **Does your project use TypeScript?** Yes
- **How would you like to define a style for your project?** Use a popular style guide
- **Which style guide would you like to follow?** airbnb
- **What format do you want your config file to be in?** JSON
-**Would you like to install them now with npm?** Yes

If you go to node_modules/.bin, you should see a file named ".eslintrc.json" Open this file, and add the following code to it: 
Next, overwrite the 
```
"rules": {
"react/jsx-filename-extension": [1, {
"extensions": [".js", ".jsx", .tsx]}
]}
```

### Installing Prettier 
To install Prettier follow these steps: 

1. In Visual Studio Code go to View ->Extensions.
2. Search for prettier code formatter
3. Click Install

Now go back to your terminal and write: 

```
npm i prettier eslint-config-prettier eslint-plugin-prettier -D
```

Now edit your ".eslintrc.json" with: 
```
"extends": [ "airbnb", "plugin:prettier/recommended" ]
```

### Making VSCode auto-format everytime the file is saved
In VSCode, go to File -> Preferences -> Settings and type format save. 
Try to check the box under "Editor: Fomrat on Save", you should get an error message in the bottom-right corner of your screen. 
Here's an image that might help: 

(https://drive.google.com/file/d/1O8l_pISjJO38Cqu61R8lNcdpNHRGN23S/view?usp=sharing)

In the error message, click on the "Open Settings" button and in the settings.json file that pops up, coy paste the following code: 
```
"eslint.alwaysShowStatus": true,
"editor.formatOnSave": true,
"[javascript]": {
   "editor.formatOnSave": false
 },
"eslint.autoFixOnSave": true,
"prettier.disableLanguages": [
    "js"
]
```
