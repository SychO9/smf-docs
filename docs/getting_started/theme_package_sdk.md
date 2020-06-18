# Theme Package SDK
Themes have a different format for the info file named `theme_info.xml`.

## Format
```xml
<?xml version="1.0"?>
<theme-info xmlns="http://www.simplemachines.org/xml/theme-info" xmlns:smf="http://www.simplemachines.org/">
    ...
</theme-info>
```

## Basic Information
* ID: `<id>username:theme_slug</id>`
* Version: `<version>1.0</version>` The version of the **theme**, this is often mistaken by the version of SMF.
* SMF Version: `<install for="2.1 - 2.1.99, 2.1 RC2"/>` The SMF version(s) it is compatible with.
* Name: `<name>Theme Name</name>`
* Author: `<author name="Author Name/Username">author@email.example</author>`
* Website: `<website>https://www.simplemachines.org/</website>`
* Template Layers: `<layers>html,body</layers>` This will call for the following functions in this exact order: `template_html_above()` `template_body_above()` `template_body_below()` `template_html_below()` which are all defined in your theme's `index.template.php`. So adding an additional layer such as `header` would call the `above` and `below` functions of said layer in the proper defined order given.
* Default Template: `<templates>index</templates>` The default template to load on startup.
* Theme Based On: `<based-on></based-on>` default value is blank.

## Full Example
```xml
<?xml version="1.0"?>
<theme-info xmlns="http://www.simplemachines.org/xml/theme-info" xmlns:smf="http://www.simplemachines.org/">
    <!-- For the id, always use something unique - put your name, a colon, and then the package name. -->
    <id>username:theme_slug</id>
    <!-- The theme's version, please try to use semantic versioning. -->
    <version>1.0</version>
    <!-- Install for, the SMF versions this theme was designed for. Uses the same wildcards used in the packager manager. This field is mandatory. -->
    <install for="2.1 - 2.1.99" />
    <!-- Theme name, used purely for aesthetics. -->
    <name>Theme Name</name>
    <!-- Author: your email address or contact information. The name attribute is optional. -->
    <author name="Author Name/Username">...</author>
    <!-- Website... where to get updates and more information. -->
    <website>https://www.simplemachines.org/</website>
    <!-- Template layers to use, defaults to "html,body". -->
    <layers>html,body</layers>
    <!-- Templates to load on startup. Default is "index". -->
    <templates>index</templates>
    <!-- Base this theme off another? Default is blank, or no. It could be "default". -->
    <based-on></based-on>
</theme-info>
```