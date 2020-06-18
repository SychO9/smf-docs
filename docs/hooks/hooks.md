## Integration Hooks
![hook](../assets/hook.png ':class=legendImage :size=197x255')
Before going any further, you need to understand what *integration hooks* are and how they can be used to extend SMF. In the codebase are certain places where integration functions are called by the system, i.e hooks, you can use this to register your own functions to specific hooks where your functions will be executed.

The code for a hook, calling integration functions, looks like this in the codebase:
```php
call_integration_hook('integrate_*', array($param1, $param2));
```

### Using Hooks
To make use of a hook, you need the `add_integration_function()` function, usually you would want to use this function upon mod installation as so:

```php
add_integration_function($hook_name, $function_name, $make_permanent);
```

The `make_permanent` parameter defaults to `true` meaning that after the above function is run, the system will permanently remember the function name and the name of the hook where it will be called. In which case the only way to remove the integration function(s) is to use the `remove_integration_function()` function.

If `make_permanent` is set to `false` the function will only be called in the hook as long as it has been added before the hook is reached, and will therefore not be permanently saved.

### Special Hooks
##### `integrate_pre_include`
This hook is used to preload files (everywhere) early in the process.
```php
add_integration_function('integrate_pre_include', '$sourcedir/YourFilePath.php');
```
`$sourcedir` refers to the sources directory of the software.

##### `integrate_{?}_quickbuttons`
The software UI has quickbuttons in multiple places, with different types, such as the ones used in the topic posts, or the ones used in the moderation reports. If you want to add more items to these lists you need to figure out the class name of the specific quickbuttons type you wish to extend. For example, for the quickbuttons in the topic posts, the quickbuttons HTML element has a class of `quickbuttons_post` therefore you need to target the `integrate_post_quickbuttons`.

### Available Hooks
Unfortunately we cannot explain in details every single hook, there are over **350** hooks in the codebase, we can only provide a list of all the existing hooks and where to find them, and then you can go to the specific spot in the code and see how you can use it for your mod.

[List of all available hooks](hooks/all_hooks.md).
