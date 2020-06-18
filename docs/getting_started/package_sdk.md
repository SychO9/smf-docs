## Package Info
Every mod needs to have a `package-info.xml` file that retains multiple information about the mod, such as the name, version, compatible SMF versions, installation process ...etc. We will go in detail about all that can be added in this file.

## Format
```xml
<?xml version="1.0"?>
<!DOCTYPE package-info SYSTEM "http://www.simplemachines.org/xml/package-info">
<package-info xmlns="http://www.simplemachines.org/xml/package-info" xmlns:smf="http://www.simplemachines.org/">
    ...
</package-info>
```

## Basic Package Information
* ID: `<id>username:package_slug</id>`
* Name: `<name>Package Name</name>`
* Type: `<type>modification</type>`: `avatar` or `language` or `modification`
* Version: `<version>1.0</version>` Package version

## Installation/Uninstallation/Upgrade Information
* Tag: `<install></install>` or `<uninstall></uninstall>` or `<upgrade></upgrade>`
* Attributes:
    - `for`: SMF Versions the package is compatible with. Example: `2.1 - 2.1.99, 2.1 RC1, 2.1 RC2`
    - `from`: Used for `upgrade` operations, the version of the mod you are upgrading from. Example: `1.0-1.5,2.0`

The install process can have various information defined.

### Hook
Adds an integration function to a specific hook. (Saves the hook information in the database)
* Tag: `<hook />`
* Attributes
    - `hook`: the name of the hook.
    - `function`: the name of the function, can be a call to a method via Class::method.
    - `file`: the file containing the function, this file will be auto added to the `integrate_pre_include` hook and therefore will always be pre loaded.
    - `reverse`: If set to `true` it will remove said integration function instead of adding it. This is usually used when uninstalling.

### Database
Run database additions/changes, unlike the other tags which you usually need to have two versions of, one in the `install` operation and the other in the `uninstall` operation. The `database` one only needs to be used in the `install` operation, SMF will then remember the mod's modifications to the database and provide the user with the ability to choose whether to undo those database edits.
* Tag: `<database></database>`
* Attributes
    - `type`: either `inline` or `file`
* Content: Code or file name to execute.

### Code
PHP Code to execute
* Tag: `<code></code>`
* Attributes
    - `type`: either `inline` or `file`
* Content: Code or file name to execute

### Directory Manipulation
Create or Remove a directory
* Tag: `<create-dir />` or `<remove-dir />`
* Attributes
    - `name`: the name of the directory **(Path if removing)**
    - `destination`: the path of the directory where you want to create this new directory

Move or Require a directory
* Tag: `<require-dir />` or `<move-dir />`
* Attributes
    - `from`: the path to the directory
    - `name`: the name of the directory
    - `destination`: the path of where you want to put this directory

### File Manipulation
Remove a file or create a blank one.
* Tag: `<create-file />` or `<remove-file />`
* Attributes
    - `name`: the name of the file
    - `destination`: the path of the directory where you want to create this new file

Move a file or require one from the package.
* Tag: `<require-file />` or `<move-file />`
* Attributes
    - `from`: the path to the file
    - `name`: the name of the file
    - `destination`: the path of where you want to put this file

### Credits
This portion will credit your work by adding a line to the forum's credits page.

?> The credits page is located in the route `?action=credits`.

* Tag: `<credit></credit>`
* Attributes
    - `url`: Link to your website.
    - `license`: License Name.
    - `licenseurl`: Link to the full license.
    - `copyright`: Copyright year
* Content: Name of the package

### Readme
Show a readme text on the install page.
* Tag: `<readme></readme>` or `<readme />`
* Attributes
    - `lang`: Language of the readme
    - `parsebbc`: If set to `true` the contents will be parsed as BBCode
    - `type`: either `inline` or `file`
* Content: Text or file name, depending on the type.

### Redirection
Redirects to the target after the execution is over.
* Tag: `<redirect></redirect>` or `<redirect />`
* Attributes
    - `url`: The target to redirect to
    - `type`: either `inline` or `file`
    - `timeout`: in milliseconds, default is *5 seconds*
* Content: Redirection text or file name, depending on the type.

### Modification
Modifies a specific file of the software.

!> Unlike previous versions, 2.1 comes with hundreds of hooks making it almost unnecessary to make source code modifications, so this is not recommended unless you have found no hook to use for your mod.

* Tag: `<modification></modification>`
* Attributes
    - `type`: either `inline` or `file`
    - `reverse`: if set to `true` the instructions will be reversed.

[Read more](https://simplemachines.org/community/index.php?topic=299670.0)

## Full Example
```xml
<?xml version="1.0"?>
<!DOCTYPE package-info SYSTEM "http://www.simplemachines.org/xml/package-info">
<package-info xmlns="http://www.simplemachines.org/xml/package-info" xmlns:smf="http://www.simplemachines.org/">
	<name>Package Name</name>
	<id>username:package_slug</id>
	<type>modification</type>
	<version>1.0.0</version>

	<install for="2.1 - 2.1.99">
		<readme type="file" parsebbc="true">README.txt</readme>
		<redirect url="?action=admin;..." timeout="3000" type="inline">You will now be redirected to the mod settings.</redirect>
		<credits url="..." license="BSD 3-clause license" licenseurl="https://opensource.org/licenses/BSD-3-Clause" copyright="2020">Package Name</credits>
		<database>database.php</database>

		<!-- files -->
		<require-file name="PackageFile.php" destination="$sourcedir" />
		<require-file name="PackageFile.template.php" destination="$themedir" />
		<require-file name="PackageFile.english.php" destination="$languagedir" />
		<require-file name="package_file.css" destination="$themedir/css" />

		<!-- hooks -->
		<hook hook="integrate_getboardtree" function="package_slug_board_index" file="$sourcedir/PackageFile.php" />
		<hook hook="integrate_modify_board" function="package_slug_modify_board" file="$sourcedir/PackageFile.php" />
		<hook hook="integrate_pre_css_output" function="package_slug_css" file="$sourcedir/PackageFile.php" />
	</install>

	<uninstall for="2.1 - 2.1.99">
		<!-- hooks -->
		<hook hook="integrate_getboardtree" function="package_slug_board_index" file="$sourcedir/PackageFile.php" reverse="true" />
		<hook hook="integrate_modify_board" function="package_slug_modify_board" file="$sourcedir/PackageFile.php" reverse="true" />
		<hook hook="integrate_pre_css_output" function="package_slug_css" file="$sourcedir/PackageFile.php" reverse="true" />

		<!-- files -->
		<remove-file name="$sourcedir/PackageFile.php" />
		<remove-file name="$themedir/PackageFile.template.php" />
		<remove-file name="$languagedir/PackageFile.english.php" />
		<remove-file name="$themedir/css/package_file.css" />
	</uninstall>

</package-info>
```