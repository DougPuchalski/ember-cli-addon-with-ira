# In-repo addon within another addon fails

To demonstrate

```
cd myapp
bower install && npm install
ember serve
```

You should see
```
version: 1.13.8
Could not find watchman, falling back to NodeWatcher for file system events.
Visit http://www.ember-cli.com/user-guide/#watchman for more info.
Cannot read property 'addonLintTree' of undefined
TypeError: Cannot read property 'addonLintTree' of undefined
    at Class.Addon.jshintAddonTree (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/models/addon.js:543:31)
    at Class.treeFor (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/models/addon.js:305:21)
    at /private/tmp/tmp/myapp/node_modules/ember-cli/lib/models/addon.js:253:32
    at Array.map (native)
    at Class.eachAddonInvoke (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/models/addon.js:251:22)
    at Class.treeFor (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/models/addon.js:298:20)
    at EmberApp.<anonymous> (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/broccoli/ember-app.js:358:20)
    at Array.map (native)
    at EmberApp.addonTreesFor (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/broccoli/ember-app.js:356:30)
    at EmberApp._processedAppTree (/private/tmp/tmp/myapp/node_modules/ember-cli/lib/broccoli/ember-app.js:616:25)
```

This will not fail without the component inside of the in-repo addon.
