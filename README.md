npm-practice is a repo containing a npm (Node Package Manager) development environment. I created it as part of how-to-npm, a command-line tutorial that helps get you started with npm.

Install the tutorial: `$ npm install -g how-to-npm`

Start the tutorial: `$ how-to-npm`

## Tutorial notes: 

#### 02 Login

See who you're logged in as: `$ npm whoami`

Create your account: `$ npm adduser`

#### 03 Start A Project

npm helps you build projects, but for npm to be able to do that, you need to tell npm a little bit about your project. You can tell npm about your project in a file called `package.json`. To create `package.json`: `$ npm init --scope=<username>`

#### 04 Install A Module

The first thing that most people do with npm is install a dependency. Dependencies are fetched from the registry (https://registry.npmjs.org), and unpacked in the `nodes_modules` folder. To install a dependency: `$ npm install <modulename>`

#### 05 Listing Dependencies

List what you have installed: `$ npm ls`

If you don't update the `package.json` when you install a dependency, the dependency will show up as 'extraneous', warning you that you have something there that you haven't listed as a dependency. To avoid this situation, either edit `package.json` yourself or use the `--save` flag when installing dependencies. You might not want to do this with things that you're just trying out, but when you decide on something, you can use this flag to update your `package.json` file easily. 

#### 06 npm Test 

npm can be used as a task runner, and almost every module and project will have a test script that runs to make sure everything is good. To get started, create a file called `test.js` and edit `package.json` to make your scripts section look like this: 

    "scripts": {
        "test": "node test.js"
    },

#### 07 Package Niceties

To see if your `package.json` is missing things that are normally expected: `$ npm install`. If it is, you can edit your `package.json` file by hand, or run `npm init` again.

#### 08 Publish

Publish a module to the registry: `$ npm publish`

View your package details, to see what you just published, and to check if a name is already taken: `$ npm view <package-name>`

You don't have to just share code for other people, though. There are also benefits to breaking up your code into small manageable pieces, even if you are only using them all yourself.

#### 09 Version

Version numbers in npm follow a standard called "SemVer", which stands for "Semantic Version". Specs can be found at http://semver.org.

    1.2.3
    ^ ^ ^
    | | `-- Patch version. Update for every change.
    | `---- Minor version. Update for API additions.
    `------ Major version. Update for breaking API changes.

The npm registry won't let you publish a new release of your package without updating the version number. 

You can update your version number either by hand in `packages.json` or with `npm version`, a command which will update your package.json` file for you, and also commit the change to git if your project is a git repository. 

Learn more about any npm command: `$ npm help <command>`

#### 11 Dist Tag

Every published package on npm has a `dist-tags` entry on it which maps strings like "latest" to version numbers like "1.2.48". 

When you publish, the version that you publish gets tagged as "latest" (which is the only tag that has any special significance to npm itself). By default, the "latest" version is what gets installed.

To publish something and not make it the default version of a package, you can manually manage these distribution tags with the `dist-tag` command. 

Add a tag to a version: `$ npm dist-tag add @briennakh/npm-practice@1.0.1 dev`

List all distribution tags: `$ npm dist-tag ls`

#### 12 Dist Tag Removal

The only dist-tag you can't ever remove is "latest". You can point "latest" to a different version: `$ npm dist-tag add @briennakh/npm-practice@1.0.0`

Remove any other tag: `$ npm dist-tag rm @briennakh/npm-practice dev

#### 13 Outdated

Detect if any of your installed packages are outdated: `$ npm outdated`

#### 14 Update

To update an outdated package, do either of the following:

* Explicitly run `npm install` to pull it in
* Update all of your deps to the max version you allow in your `package.json`: `$ npm update`

#### 15 Rm 

Remove a package: `$ npm uninstall <package-name>`

Just like you can use `--save` on installing packages, you can also use `--save` when removing packages, to also remove them from your `package.json` file. 

#### 16 Finale

To learn more about all the fun I and npm can have together: www.npmjs.com
    