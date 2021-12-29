# eat
A small package manager that I made for fun using bash scripts.

## packages
Note: I have left an example package in the directory structure called ```bobsson.tar.gz```.

The packages are just .tar.gz files that contain a directory with the package name. This is an example structure:

```
package_name
	- package.conf
	- home
		- package_name_executable_or_whatever
```

A typical package.conf will look something like this:
```
name=package_name
desc=a package
priority=3
files=home/package_name_executable_or_whatever
```
Package file names in the ```files``` field can be seperated by the ```:``` character.

Package priority at the moment doesn't have any purpose; However, when I add the ability to remove packages, these will be the priority options:
	- 1: The package is an extremely vitally important package that cannot/shouldn't be removed
	- 2: The package is not extremely important, but still important enough that it isn't recommended to be removed
	- 3: The package is pretty/completely unimportant and probably okay to remove

### to create a package
- Make sure your have the package.conf configuration file and the files to be installed along with the package such as ```/bin/executable_name```. Put these files in a directory with your desired package name.
- Run ```./eat-create <package_name>``` to create the tar.gz file for the package.

## commands
You can use ```eat inst <package_name.tar.gz>``` to install a package, ```eat show <package_name>``` to show the information of an already installed package, ```eat list``` to list all of the installed packages, or ```eat help``` to display the help dialog.

Right now, I would like to add the ability to remove packages, and maybe even the ability to install a package from a repository.

## to install eat onto your system
To install eat onto your system, run the ```eat-install``` script.
