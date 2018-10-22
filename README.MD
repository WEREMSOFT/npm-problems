Steps to reproduce:

Delete node_modules folder(if exists)
Add version ^1.2.1 for lodash
npm Install
Notice that package-lock has it's value to "1.3.1" for lodash and there is no node_modules on wordo
Modify package.json to be ^2.0.0 for lodash.
Run npm install. Note that package.json has changed.
Note that htere is node_modules for wordo

npm modifies the package-lock.json if there is a new version in the npm directory. This is source of high discussion in the comunity since this behavior is not well documented.

What was done?

Modified the .nprc file with options that prevents this file to be modified.


Other cases that the package-lock.json file is modified:

* Optional library is added to package.json
* A plataform dependend library is not necesary for the current platform, like fsevents. Will be removed in linux, will be added in mac.
