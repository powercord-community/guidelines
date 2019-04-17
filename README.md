# Powercord Community Guidelines

## 1. Properly structure your plugin's manifest

All Powercord plugins require a valid `manifest.json` file.
This file is used internally to give information about the plugin to the end user, as well as define how the plugin
will behave (Should it be injected in the overlay? Does it have dependencies?)

| Key                  | Description                                                                                                      | Optional |
|----------------------|------------------------------------------------------------------------------------------------------------------|:--------:|
| name                 | Display name used in the UI.                                                                                     |          |
| version              | Version of the plugin. 0.x.x will mean beta and will be flagged as so in the plugins section.                    |          |
| description          | Short description of what the plugin is doing.                                                                   |          |
| author               | Name(s) of the author(s).                                                                                        |          |
| license              | License the plugin is released under.                                                                            |          |
| permissions          | List of permission the plugin is asking (`keypresses`, `use_eud`, `ext_api`).                                    | x        |
| dependencies         | List of plugin's dependencies.                                                                                   | x        |
| optionalDependencies | List of plugin's optional dependencies. Will only affect load order to ensure the plugin is loaded before yours. | x        |
| appMode              | Where the plugin should be injected. Can be `app`, `overlay`, or `both` (default to `app`).                      | x        |

## 2. Follow Discord and other services ToS

Even if Powercord is by nature against Discord ToS, it doesn't mean that you're allowed to do everything you want. For
example scraping End User Data without consent is forbidden.

## 3. No circumvention of Discord permissions

Do not circumvent Discord permissions as well as attempt to bypass something restricted by the Discord client. This can be a potential security breach or invasion of privacy (e.g. showing hidden channels is an invasion of staff privacy, storing
deleted messages forever is an invasion of author's privacy (and forbidden by Discord ToS).

## 4. Meet a certain standard performance wise

Plugins that are heavy in terms of resource usage are not great for the user experience. Slower computers may not
be able to run smoothly if your plugin is doing resource-heavy tasks, for example having mutation observers.

If you do need to perform resource-heavy tasks, try using a [web worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

## 5. Do not write harmful plugins

Harmful plugins that abuse Powercord APIs or Discord internals to do malicious things like spambots, keyloggers
or anything else are strictly prohibited.

## 6. Do not have bad privacy practices

Collecting user data using Powercord without consent is forbidden. All features that require the collection of user data
should be opt-in, and if your plugin is based on user data please specify it in `permissions` manifest key.

## 7. Limit use of external APIs

External APIs, even open source, may secretely do malicious actions, as returning malicious data, logging your IP address
and more. If you have to use your API or another one that is not provided by a well-known entity (like Spotify API),
please add the `ext_api` permission to your manifest.

## 8. Do not break other plugins

Your plugin should be able to run in a way that it'll **not** affect any other plugin installed. We internally made
sure everything will run smoothly even if multiple plugins are patching the same component.

## 9. Prefer contributing instead of duplicating

If you want to make a plugin that already exists, prefer contributing to the already existing plugin than having another
plugin with the same purpose.

## 10. Do **NOT** perform manual HTTP requests to Discord or the Gateway

Discord internally has everything you'll need to retrieve data without directly calling the API or connecting to the
Gateway. Performing such actions may get user's account flagged for selfbotting or modding and banned for doing so.

## 11. Powercord Developers will never directly push in your plugin's repo

Even if we have full access by being administrators of the organization, we'll never push to a plugin's repo unless
we're invited to do so. We'll always prefer forking and making a PR.

<!--
## 420. No derpyware
:^)
-->
