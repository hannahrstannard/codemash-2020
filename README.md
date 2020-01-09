# CodeMash 2020

Contains the slide deck used for my presentation, along with my speaker notes. The README contains the steps I used in the demo, so if you want to recreate the project from this talk, you can!


## Set Up Project
First, we want to create the project directory. Rather than use Git for this project and then clone the repo, we will just make an empty folder and navigate into it.

```bash
cd ~
mkdir codemash
cd codemash
```

Next, we will go ahead and initialize the project. This will create a package.json file, which contains the project configuration. The package.json file will keep track of the libraries used in the project, which includes ESLint.

```bash
npm init -y
```

The `-y` option for the `npm init` command means it won’t ask for confirmation every time. Instead, it will automatically answer “yes” everytime there is a question.


## Set Up ESLint
After initializing the project, the next step we will be doing is installing ESLint. This will create a “node_modules” folder, a directory where packages we install with NPM are stored.

```bash
npm install eslint
```

Now that we have installed ESLint, we need to initialize it. This will create our configuration file with an empty rule set.

```
npx eslint --init
```


## Run ESLint
We want to go ahead and create a JavaScript file so that ESLint will have something to run on.

```bash
nano my-file.js
```

This will create a file and open it up for you to edit. We will want to add the following:

```javascript
const helloWorld = “Hello World!”;

console.log(helloWorld);
```

Write it to the file, then close the editor.

Once we have our simple JavaScript file created, we can go ahead and run ESLint on it.

```bash
npx eslint my-file.js
```

If there are errors or warnings produced by ESLint, you might be able to fix some of them automatically by adding `--fix` when running ESLint:

```bash
npx eslint my-file.js --fix
```

This can be helpful when running against an entire project so that you don’t have to spend all of your time hunting down stray semicolons, double quotes, etc. in your file.

If you want to run ESLint on multiple files:
```bash
npx eslint *.js
```


## Configure ESLint
[ESLint already defines many rules for you to use in your project.](https://eslint.org/docs/rules/) You do not have to create your own rules to be able to fully use ESLint, though you can if you want.

Let’s say you wanted all switch statements to implement a default case using ESLint’s default-case rule. If you wanted an error to be produced if a default case was not provided with a switch statement:

```javascript
"default-case": "error"
```

If you wanted a warning to be produced if a default case was not provided with a switch statement:

```javascript
"default-case": "warn"
```

If you wanted it to do nothing if a default case was not provided with a switch statement:

```javascript
"default-case": "off"
```

Depending on the result you asked for ESLint to provide when finding a switch statement without a default case, when you run ESLint on your file, you'll find that this rule is now active.


# Congrats!
You have now successfully installed ESLint and run it on your project.
