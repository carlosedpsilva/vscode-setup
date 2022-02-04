# vaaaarlos' vscode setup

Welcome to my VS Code setup!

The key to my setup is the [Profile Switcher](https://marketplace.visualstudio.com/items?itemName=aaronpowell.vscode-profile-switcher) extension, which allows you to switch between different profiles of settings and extensions. Combined with the built-in [Settings Sync](https://code.visualstudio.com/docs/editor/settings-sync) extension, this allows you to easily share your profiles across multiple computers.

Say goodbye to a slow and painful VS Code experience!

## Summary

Make sure you understand  how to use the [Profile Switcher](https://marketplace.visualstudio.com/items?itemName=aaronpowell.vscode-profile-switcher) extension before you start.

I've set up my VS Code settings and extensions in a profile called "Main", as shown in the tables [below](#table-of-contents). The "Main" profile is the default profile and should be used as the base for all new profiles.

If you want to create a **specific profile**, you can do so by copying mine or your own "Main" profile and then adding the extensions you want to use to your profile on your `settings.json`. All the extensions settings of this specific profile should be saved in the settings of the workspace you're working on.

Please notice that the way I set up my profiles doesn't save any settings, so if you want to change the settings of a **specific profile**, you have to backup it yourself add it to your workspace settings on the `.vscode/settings.json` file.

Make sure to backup all your settings and extensions and keep them in a way that you can easily maintain and update.

## Setup

I've compiled a list of extensions and settings that I like to use in the [vscode-settings](vscode-settings) and [vscode-extensions](vscode-extensions) folders of this repository, respectively. All you need to do is install the [Profile Switcher](https://marketplace.visualstudio.com/items?itemName=aaronpowell.vscode-profile-switcher) extension, create a profile with the extensions you want to use, and then switch to that profile. It'll download all the extensions for you and locally backup them when you switch to another profile instead of simply uninstalling them, making the context switching faster and easier as it'll no longer have to download the extensions again.

As you can see in my main [settings](vscode-settings/settings-main.jsonc) file, a profile is set up on the `settings.json` file with the following settings:

```jsonc
{
    "profileSwitcher.profiles": ["Name of your profile"],

    "profileSwitcher.storage": {
        "Name of your profile": {
            // the settings of your profile will be stored here
        }
    },

    "profileSwitcher.extensions": {
        "Name of your profile" [
            // the extensions of your profile will be stored here
        ]
    }
}
```

So all you need to do is copy and paste the extensions you want in the array of extensions for your profile under the `profileSwitcher.extensions` key. Check my [settings](vscode-settings/settings-main.jsonc) file for an example.

### Attention

Note that all the formatting of your `settings.json` is lost when you switch profiles. That's why it's important to backup your settings as I did if you care about formatting. It'll also be a lot harder to maintain and update your settings if you don't.

### Step-by-step

1. Enable Settings Sync. Sync all your data.
2. Install the [Profile Switcher](https://marketplace.visualstudio.com/items?itemName=aaronpowell.vscode-profile-switcher) extension.
3. Disable the synchronization for extensions (`Ctrl+Shif+P` > Settings Sync: Configure... > Uncheck 'Extensions')
4. Create a local or remote (like I did with this repository) backup of your settings. See the [notice](#attention) above.
5. Create a Profile Switcher profile.
   - You can create an empty profile by manually adding an entry to the `profileSwitcher.profiles` array in your `settings.json` file.
   - You can also create a profile for the current settings and extensions by using the 'Save Profile' command (`Ctrl+Shift+P` > Profile Switcher: Save Profile). In this case, jump to the next step.
     - Please notice that you'll lose all the formatting of your `settings.json` file. Back up your settings before you do that.
6. Update your profile by adding the extensions you want to use from my [vscode-extensions](vscode-extensions) profiles, or by installing them manually and them saving your profile.
7. In the `.vscode/settings.json` file of the workspace you're working on, add the specific extension settings of your profile.
8. All set!

After switching profiles, I can simply paste my [main](vscode-settings/settings-main.jsonc) settings to my `settings.json` to restore the formatting, as all the specific settings will be saved in the workspace settings. You can do the same if you create a main settings file yourself.

## Table of Contents

For a quick overview of the different settings and extension profiles I use, I've included a table of contents below.

### Settings

| ----- Title ----- | -------------- Description -------------- | File                                               |
| ----------------- | ----------------------------------------- | -------------------------------------------------- |
| Vanilla Settings  | Settings for my vanilla VS Code profile   | [link](vscode-settings/settings-vanilla.jsonc)     |
| Main Settings     | Settings for my main VS Code profile      | [link](vscode-settings/settings-main.jsonc)        |
| Keybindings       | General keybindings settings              | [link](vscode-settings/settings-keybindings.jsonc) |

### Extensions Profile Folders

| ----- Title ----- | -------------- Description -------------- | Folder                           |
| ----------------- | ----------------------------------------- | -------------------------------- |
| Main              | Plain VSCode usage profiles               | [link](vscode-extensions/main)   |
| Java              | Java coding profiles                      | [link](vscode-extensions/java)   |
| Web               | Web coding profiles                       | [link](vscode-extensions/web)    |
| Other             | Other coding profiles and utilities       | [link](vscode-extensions/other)  |
| Remote            | Remote coding profiles                    | [link](vscode-extensions/remote) |
