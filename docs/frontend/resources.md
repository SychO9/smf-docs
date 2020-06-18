## Loading resources
There are many hooks you can use to load more resources, as long as the hook is reached before the `template_javascript` and `template_css` functions.`integrate_load_theme` is one of these hooks, all you need to do is use the `loadCSSFile` and `loadJavaScriptFile` functions.

You can find the function definitions here: [`loadCSSFile`](#), [`loadJavaScriptFile`](#)

example:
```php
function mod_slug_resources()
{
    // A file located in the theme's css folder (or the default theme's)
    loadCSSFile('file.css', array('force_current' => false, 'minimize' => true), 'mod_slug');

    // An external resource
    loadCSSFile('https://.../file.css',
        array(
            'external' => true,
            'attributes' => array(
                'integrity' => '...',
                'crossorigin' => '...'
            )
    ));
}
```

## Adding inline CSS/JavaScript Code
You can use the [`addInlineJavaScript`](#) and [`addInlineCss`](#) functions. You can also define javacript variables using the [`addJavaScriptVar`](#) function.