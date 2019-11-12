# Powercord Community Guidelines

Those guidelines are set to ensure Powercord's ecosystem stays as awesome as possible, and to avoid malicious plugins,
or bad performances. The Powercord Staff will enforce **all** of those guidelines and take decisions we consider
appropriate for plugins not complying with those guidelines, at our sole discretion.

**Note**: We may decide, depending on the context, to let a plugin that would not be compliant with those guidelines
pass. Those exceptions will be made at our sole discretion.

## The rules

Everything you build for Powercord will have to follow those rules.

### 1. Properly structure your plugin's manifest

All Powercord plugins require a valid `manifest.json` file.
This file is used internally to give information about the plugin to the end user, as well as define how the plugin
will behave (Should it be injected in the overlay? Does it have dependencies?)

### 2. Follow Discord and other services ToS

Even if Powercord is by nature against Discord ToS, it doesn't mean that you're allowed to do everything you want. For
example scraping End User Data without consent is forbidden.

### 3. No circumvention of Discord permissions

Do not circumvent Discord permissions as well as attempt to bypass something restricted by the Discord client. This can
be a potential security breach or invasion of privacy (e.g. showing hidden channels is an invasion of staff privacy,
storing deleted messages forever is an invasion of author's privacy (and forbidden by Discord ToS)).

### 4. Meet a certain standard performance wise

Plugins that are heavy in terms of resource usage are not great for the user experience. Slower computers may not
be able to run smoothly if your plugin is doing resource-heavy tasks, for example having mutation observers.

If you do need to perform resource-heavy tasks, try using a [web worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers).

### 5. Do not write harmful plugins

Harmful plugins that abuse Powercord APIs or Discord internals to do malicious things (including but not limited to
spambots, keyloggers, scrapers, ...) are strictly prohibited.

### 6. Respect users privacy

Collecting user data using Powercord without consent is forbidden. All features that require the collection of user data
should be opt-in (if possible), and properly reflect data collection with the `permissions` manifest key.

### 7. Limit use of external APIs

External APIs, even open source, may secretely do malicious actions, as returning malicious data, logging your IP
address and more. If you have to use your API or another one that is not provided by a well-known entity (like Spotify
API), please add the `ext_api` permission to your manifest.

**Note**: If your plugin requires the use of an external custom-built backend, Powercord is ready to hook you up with
free hosting and domain (`yourplugin.powercord.dev`). [More about that here](https://github.com/powercord-community/suggestions#about-backends).

### 8. Avoid breaking other plugins

Your plugin should be able to run, no matter what plugins the user installed. We internally have some protection to help
preventing conflicts, but we can't do everything for you. If your plugin happens to be incompatible with another, try
discussing with the plugin developer.

### 9. Prefer contributing instead of duplicating

If you want to make a plugin that already exists, prefer contributing to the already existing plugin than having another
plugin with the same purpose.

### 10. Only perform manual HTTP requests to Discord if there are no other solutions

Discord internally has mostly everything you'll need to retrieve data without directly calling the API or connecting to
the Gateway. Performing such actions may get user's account flagged for selfbotting or modding and banned for doing so.

### 11. Limit NSFW plugins

We're not against plugins providing NSFW features, but they should be properly labeled and handled. If you plugin can
provide NSFW but it isn't the main purpose, **NSFW features must be turned off by default**. If the main feature of
the plugin is based on NSFW, please specify it in your manifest through the `nsfw` key, so we can label it as such.

## How we handle plugins

### Size doesn't matter

This is also true for plugins. Your plugin can be very feature rich with thousands of lines of code, or just a few
lines. As long as they bring a feature, we'll accept it.

To quote aetheryx,
> plugins are like boobs<br>
> small, big, it doesn't matter, we love them all

### We'll always let people decide how they write their code

When reviewing plugins, we won't impose any specific code style, license or anything. Your code, your choices. We'll
recommend some good practices (like not mixing `"` and `'` for example), but won't reject your plugin because of it.

### We will never directly push to your plugin's repo

Even if we have full access by being administrators of the organization, we'll never push to a plugin's repo unless
we're invited to do so. We'll always prefer forking and making a PR. It's your plugin, and we don't have to push
