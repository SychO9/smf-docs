# Quick Start
This is only a quick guide on making a mod (or theme) for SMF2.1, along the way many links will be provided that will allow you to dig deeper and learn about extending SMF2.1 in more detail.

!> This guide is meant for people who are familiar with coding.

## Making a Mod
We will try to make a simple quick mod that adds a new page to our forum and prints a classic `Hello World!`.

1. In a new directory, start by creating a `package-info.xml` file for your mod, this file will contain various information that will be required by the software ([Read More](getting_started/package_sdk.md)). Fill the basic information:
```xml
<?xml version="1.0"?>
<!DOCTYPE package-info SYSTEM "http://www.simplemachines.org/xml/package-info">
<package-info xmlns="http://www.simplemachines.org/xml/package-info" xmlns:smf="http://www.simplemachines.org/">
    <name>Package Name</name>
    <id>username:package_slug</id>
    <type>modification</type>
    <version>1.0.0</version>
</package-info>
```

2. Next, create a `Sources` directory, and inside create the following files:
    * `Subs-QuickyMod.php`: This file will contain our integration functions.
    * `QuickyMod.php`: This file will contain source code for our new page

3. Create another directory in the root, called `Themes` and inside this directory create another directory `default`, and lastly create the following files:
    * `QuickyMod.template.php`: this will contain the HTML code of our new page.
    * `languages\QuickyMod.english.php`: this will contain our newly added language strings. (**careful, it needs to be inside a languages directory**)

4. Before we start filling these files, we will go back to the `package-info.xml` file where we add new install/uninstall operations with our hooks and files:
```xml
<install for="2.1 - 2.1.99">
    <!-- Files -->
    <require-dir name="Sources" destination="$boarddir" />
    <require-dir name="Themes" destination="$boarddir" />

    <!-- Hooks -->
    <hook hook="integrate_actions" function="quickymod_actions" file="$sourcedir/Subs-QuickyMod.php" />
    <hook hook="integrate_menu_buttons" function="quickymod_menu_buttons" file="$sourcedir/Subs-QuickyMod.php" />
</install>
<uninstall for="2.1 - 2.1.99">
    <!-- Files -->
    <remove-file name="$sourcedir/QuickyMod.php" />
    <remove-file name="$sourcedir/Subs-QuickyMod.php" />
    <remove-file name="$themedir/QuickyMod.template.php" />
    <remove-file name="$languagedir/QuickyMod.english.php" />

    <!-- Hooks -->
    <hook hook="integrate_actions" function="quickymod_actions" file="$sourcedir/Subs-QuickyMod.php" reverse="true" />
    <hook hook="integrate_menu_buttons" function="quickymod_menu_buttons" file="$sourcedir/Subs-QuickyMod.php" reverse="true" />
</uninstall>
```
!> Notice how in the uninstallation process we have to specifically remove every single file.

5. Now we will create the integration functions that we need, you must have noticed that we have specified two hooks, `integrate_actions` is to create a route for our new page. `integrate_menu_buttons` is to add a new button to the forum's main menu that will lead to our page.
    1. Let's start by creating the `quickymod_actions` that will add a new route through the `integrate_actions` hook. Remember this function goes inside `Subs-QuickyMod.php`.
    ```php
        function quickymod_actions(&$actionArray)
        {
            // We define the route (action) name and the file that handles that route.
            // We also specify the entry function, in this case QuickyMod
            // array('action_name' => array('file_name.php', 'entry_function_name'))
            $actionArray += array('quickymod' => array('QuickyMod.php', 'QuickyMod'));
        }
    ```
    2. Now we will add a new menu button, by creating the `quickymod_menu_buttons` function that is hooked to `integrate_menu_buttons`.
    ```php
        function quickymod_menu_buttons(&$buttons)
        {
            global $scripturl, $txt;

            // Load our language file, we will later fill the language file
            loadLanguage('QuickyMod');

            $buttons['quickymod'] = array(
                'title' => $txt['quickymod'], // We will later define this language string
                'href' => $scripturl . '?action=quickymod', // We have previously defined a route(action) with the name quickymod
                'show' => true,
                'icon' => 'frenemy', // a link to a list of all possible icons is provided below
            );
        }
    ```
    ?> You can find [here](frontend/icons.md) a list of all available icon names.

6. On to the `QuickyMod.php` file where we define the backend code for our page.
```php
function QuickyMod()
{
    global $context, $txt;

    // Load our template file
    loadTemplate('QuickyMod');

    // Define the page's title
    $context['page_title'] = $txt['quickymod']; // We have already loaded our language file using the integrate_menu_buttons hook

    // Append a new item to the linktree
    $context['linktree'][] = array(
        'url' => $scripturl. '?action=quickymod',
        'name' => $txt['quickymod'],
    );
}
```

7. In `QuickyMod.template.php` we have access to the `$context` variable which we can fill with any data we need from our source code in `QuickyMod.php`. Right now we will only print a simple example message.
```php
// the default function for template files is template_main()
// you can use a different function by defining $context['sub_template'] = 'different_function';
// in the source file QuickyMod.php, then you'd have to define a template_different_function() function in this file
function template_main()
{
    global $txt;

    echo $txt['hello_world'];
}
```

8. Finally, we just have to define the language strings that we have used in the various previous files, in `QuickyMod.english.php` (**Translation is as simple as creating a new file with another language name than `english`**).
```php
$txt['quickymod'] = 'Quicky Mod';
$txt['hello_world'] = 'Hello World!';
```