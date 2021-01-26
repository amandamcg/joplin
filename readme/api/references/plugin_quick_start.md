# Plugin: Quick Start

This includes basic info for creating a new Joplin plugin. For more details on how to scaffold a plugin, see [Plugin: Introduction](https://joplinapp.org/api/get_started/plugins/) 

## Development
To main two files for development are:

- `/src/index.ts`, which contains the entry point for the plugin source code.
- `/src/manifest.json`, which is the plugin manifest. It contains information such as the plugin a name, version, etc.

## Building the plugin

The plugin is built using Webpack, which creates the compiled code in `/dist`. A JPL archive will also be created at the root, which can use to distribute the plugin.

To build the plugin, simply run `npm run dist`.

The project is setup to use TypeScript, although you can change the configuration to use plain JavaScript.

## Updating the plugin framework

To update the plugin framework, run `npm run update`.

### Warning
In general, this command tries to do the right thing - in particular, it merges the changes in package.json and .gitignore instead of overwriting. It will also leave "/src" and this README.md untouched.

The file that may cause problem is "webpack.config.js" because it gets overwritten. For that reason, if you need to edit it, consider creating a separate JavaScript file `my-webpack.config.js` and include at the top of in webpack.config.js, i.e.  `import 'my-webpack.config.js'`. That way, when you update, you only have to restore the line that include your changes

---

N.B. This is very similar content to https://github.com/laurent22/joplin/edit/dev/packages/generator-joplin/generators/app/templates/README.md
