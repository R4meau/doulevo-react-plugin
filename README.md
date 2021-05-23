# doulevo-react-plugin

A Reactjs plugin for [Doulevo](https://github.com/doulevo/doulevo). It uses Create React App (CRA).

For Nextjs, there will be a different plugin available soon.
## Usage

This documentation assumes you [already installed Doulevo on your system](https://github.com/doulevo/doulevo/#readme).

### Creating a new React project

Use the following command to create a new React project using this plugin, directly from GitHub:
```
doulevo create <my-project> --force --plugin-url=https://github.com/r4meau/doulevo-react-plugin.git --debug
```

Replace `<my-project>` with your project/directory name.

Then cd into your new directory. You will notice your new React project and your `doulevo.json` configuration file:
```
cd <my-project>
ls -la
```

### Running in development

In development mode, your React app will still autoreload on file change. Simply run the following command within your directory to get it running:

```
doulevo up --plugin-url=https://github.com/r4meau/doulevo-react-plugin.git --debug
```

## About the templates

This plugin comes with two templates:

- react-ts
- react-js

The templates are based off the default CRA JS/TS generated starter files. As you can see in the `package.json` file, they were generated using CRA version 4.0.3.


**For contributors to this plugin:** To update CRA, [follow this guide](https://create-react-app.dev/docs/updating-to-new-releases). To update React, [follow this one](https://stackoverflow.com/a/49829751/927559). Then send us a pull request.

You have to do this for both the `-ts` and the `-js` versions.

## Functionalities

- [ ] Asks user to pick whether they want to use JS or TS
- [ ] Asks use for the initial version number of their project (for their `package.json`)
- [ ] Provides a base documentation in the README.md file
