---
title: Command Line Tool
---

The octopod-jekyll command line commands are:

```
$ octopod b[uild]
# builds from current path . to ./_site

$ octopod build <path/to/target>                   
# compiles and builds the site from the current path . to path/to/target

$ octopod build <path/to/source> <path/to/target>  
# compiles from source_path to  path/to/target

$ octopod import <importer name> <options>
# imports posts using named import script

$ octopod setup
# Sets up Jekyll site to become podcast-aware, copies assets and default config.
# Asks for confirmation on file overwrite.

$ octopod episode
# adds a post for a new episode

$ octopod deploy
# deploys your site via rsync

$ octopod <command> --help
# for more information on a specific command.

$ octopod s[erver]
# Starts the server
```

Configuration is read from `<source>/_config.yml` but can be overridden.
Available options are documented in `_config.yml`.
In case, you deleted some of the options, a full reference can be found in `_config.yml.sample`.

All derived Jekyll command line tasks can be found in Jekyll's [Usage Documentation](http://jekyllrb.com/docs/usage/), 
from which the octopod command inherits most of its functionality.
