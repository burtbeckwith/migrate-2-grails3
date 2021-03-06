## migrate-2-grails3
A Grails 2 plugin that performs a partial migration of a Grails 2 plugin or application to Grails 3

### Usage

- Create an empty Grails 3 application or plugin (depending on what you're migrating) 
- Install this plugin in the Grails 2 project being migrated, i.e. add the following to `BuildConfig.groovy`
replacing `${version}` with the latest version of this plugin

````
plugins {
    build ':migrate2-grails3:${version}'
    // other plugin dependencies
}
````

- Ensure that the current Grails version matches that of the Grails 2 project and execute the following command in the Grails 2 project

`grails migrate [path-to-grails3-project]`
    
#### Arguments

- `path-to-grails3-project` the *relative* path from the Grails 2 project to the empty Grails 3 project

### Automatic Migration Tasks

The plugin performs the tasks listed in the "Project Structure Changes" section of the [migration guide](https://grails.github.io/grails-doc/latest/guide/upgrading.html).
After following the instructions above, if the project being migrated is a plugin, steps 1-3 of the [Upgrading Plugins](https://grails.github.io/grails-doc/latest/guide/upgrading.html#upgradingPlugins)
section will also have been performed. if the project being migrated is an application, steps 1-2 of the 
[Upgrading Applications](https://grails.github.io/grails-doc/latest/guide/upgrading.html#upgradingApps) section will have been performed.
 
#### Exceptions
 
Some of the steps described in the aforementioned sections of the migration guide are not performed by this plugin. These are:

- merging `DataSource.groovy` and `Config.groovy` into a single `application.yml` or `application.groovy` config file with log4j config removed
- configuring logging via `logback.groovy`
- migrating dependencies from `BuildConfig.groovy` to `build.gradle`
