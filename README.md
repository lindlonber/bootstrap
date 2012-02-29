CommCareHQ Bootstrap, forked from Twitter Bootstrap
===================================================

HQ Bootstrap is a flavor of Twitter Bootstrap designed to work specifically with [CommCare HQ](https://github.com/dimagi/commcare-hq).
It provides all of the styling and basic javascript for HQ's user interface.

HQ Bootstrap Requirements
-------------------------

The following instructions are for *nix users. For windows installation, skip ahead to the bottom of this section.

### nodejs

Both lessc and uglify-js below need nodejs to run. [How to install nodejs](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager).

### lessc

The LESS CSS compiler is required to compile all the .less files from hq-boostrap.

Do the following to install `lessc`.

+ `sudo git clone https://github.com/cloudhead/less.js.git /opt/lessc`
+ add `alias lessc='nodejs /opt/lessc/bin/lessc'` to your bash profile

**Note to OSX users:**

Instead of adding the lessc alias, on Mac OS X you should put the lessc executable on the path, e.g. by adding `/opt/lessc/bin/` to the path.

This [LESS app](http://incident57.com/less/) is super useful for working with LESS.
It's highly recommended that you use this when making changes to the .less files. Use this along side the `make extra` command described below for updating changes to javascript or image files.

### uglify-js

Check the README for [uglify-js on GitHub](https://github.com/mishoo/UglifyJS) for instructions of how to install uglify-js for your system.

The following should work:

    ## clone the repository
    mkdir -p /where/you/wanna/put/it
    cd /where/you/wanna/put/it
    git clone git://github.com/mishoo/UglifyJS.git

    ## make the module available to Node
    mkdir -p ~/.node_libraries/
    cd ~/.node_libraries/
    ln -s /where/you/wanna/put/it/UglifyJS/uglify-js.js

    ## and if you want the CLI script too:
    mkdir -p /usr/bin
    cd /usr/bin
    ln -s /where/you/wanna/put/it/UglifyJS/bin/uglifyjs
    # (then add /usr/bin to your $PATH if it's not there already)

Make sure the user you want to use uglifyjs has the .node_libraries directory properly configured in their home dir.


### Installation for Windows Users

Installing the prerequisites on windows is actually quite painless. Install node.js via the latest .msi installer. Then install the dependencies using:

+ npm install less
+ npm install uglify-js

After you're done just update your PATH environment variable to include the bin/ directories containing the lessc and uglifyjs commands. 


Building Bootstrap
------------------

From the root directory of [commcare-hq](https://github.com/dimagi/commcare-hq) run:

    python manage.py make_bootstrap


### Having some aliasing issues?

The following arguments to this management command may help:

+ `direct-lessc` - runs `lessc` directly from `/opt/lessc`

+ `direct-uglifyjs` - runs `uglifyjs` directly from `/opt/UglifyJS`

+ `node` - used in addition to `direct-lessc` for when your OSX install of nodejs is for some reason accessed using `node` instead of `nodejs`.


Authors of Twitter Bootstrap
----------------------------

**Mark Otto**

+ http://twitter.com/mdo
+ http://github.com/markdotto

**Jacob Thornton**

+ http://twitter.com/fat
+ http://github.com/fat


Copyright and license
---------------------

Copyright 2012 Twitter, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

