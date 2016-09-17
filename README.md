npm-practice is a repo containing a npm development environment. I created it as part of how-to-npm, a command-line tutorial that helps get you started with npm.

Install the tutorial: `$ npm install -g how-to-npm`

Start the tutorial: `$ how-to-npm`

## Tutorial notes: 

#### Lesson 02

To see who you're logged in as: `$ npm whoami`

To create your account: `$ npm adduser`

#### Lesson 03 

npm helps you build projects, but for npm to be able to do that, you need to tell npm a little bit about your project. You can tell npm about your project in a file called package.json. To create package.json: `$ npm init --scope=<username>`


#### 04

The first thing that most people do with npm is install a dependency. Dependencies are fetched from the registry (https://registry.npmjs.org), and unpacked in the `nodes_modules` folder. To install a dependency: `$ npm install <modulename>`

#### 05

To list what you have installed: `$ npm ls`

If you don't update the package.json when you install a dependency, the dependency will show up as 'extraneous', warning you that you have something there that you haven't listed as a dependency. To avoid this situation, either edit package.json yourself or use the `--save` flag when installing dependencies. You might not want to do this with things that you're just trying out, but when you decide on something, you can use this flag to update your package.json file easily. 

#### 06 

npm can be used as a task runner, and almost every module and project will have a test script that runs to make sure everything is good. To get started, create a file called `test.js` and edit `package.json` to make your scripts section look like this: 

    "scripts": {
        "test": "node test.js"
    },

#### 07

To see if your `package.json` is missing things that are normally expected: `$ npm install`. If it is, you can edit your package.json file by hand, or run `npm init` again.

#### 08

To publish a module to the registry: `$ npm publish`

To view your package details, to see what you just published, and to check if a name is already taken: `$ npm view <package-name>`

You don't have to just share code for other people, though. There are also benefits to breaking up your code into small manageable pieces, even if you are only using them all yourself.

    