# insomnia-plugin-save-variables

An [Insomnia](https://insomnia.rest) Plugin that saves values from responses into variables.

## Use-Case

Insomnia supports [request chaining](https://support.insomnia.rest/article/175-chaining-requests)
, but sometimes you have multiple requests that could feed into a second
request. For example, Request A might return a Ticket Number or a Resource ID
which is used as input by Request Z. Request B might also return a similar ID which
could be used by Request Z. This is problematic for request chaining
because you would have to create copies of Request Z, one for Request A
and one for Request B.

This plugin allows you to save a value from a response, which allows
multiple requests to all save to the same variable. You can use the
variable as an input to the second request.

To continue the example above, Request A could save the ID to a variable,
"id", and Request B could save its ID to the same variable. Request Z
would only have to reference the variable itself instead of the previous
two requests. Request Z would apply to whichever request, A or B, was
run most recently.

## Installation

Install the `insomnia-plugin-save-variables` plugin from Preferences > Plugins.

## How to Use It


## Development

Create a `.env` file in this repo with the following contents:
```
# Set to the location of the insomnia plugins folder (in Insomnia, go to
# Preferences -> Plugins, then click Reveal Plugins Folder)
# Default values are:
# MacOS: ~/Library/Application\ Support/Insomnia/plugins/
# Windows: %APPDATA%\Insomnia\plugins\
# Linux: $XDG_CONFIG_HOME/Insomnia/plugins/ or ~/.config/Insomnia/plugins/
PLUGINS_DIRECTORY=/mnt/c/Users/your_username/AppData/Roaming/insomnia/plugins
```

To install the plugin into Insomnia locally, run `install-plugin.sh`, then
refresh plugins in Insomnia or restart Insomnia.