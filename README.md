> A modular UI customization for Firefox, removing borders in the favor of shadows to emphasize the layer elevation.\
> Sidebery is used for the vertical tabs.

![Preview](assets/preview.gif "Preview")

## Install

1. Set Firefox theme to Dark: `Settings > Extensions & Themes > Themes > Dark`.
2. Vertical tabs:
    * Install the [Sidebery extension](https://addons.mozilla.org/en-US/firefox/addon/sidebery/).
    * `Sidebery settings > Help > Import addon data > Choose file "Sidebery/settings.json"`.
    * *(Optional)* For tab previews: `Sidebery settings > Search for "Tabs preview" > Enable and grant permissions`.
3. Go to `about:config` (in the URL bar) and set `toolkit.legacyUserProfileCustomizations.stylesheets = true`.
4. Go to `about:support` > `Search for "Profile Directory" > Open > Copy the "chrome" folder to this location`.
5. Restart Firefox.

## Uninstall

Set `toolkit.legacyUserProfileCustomizations.stylesheets = false` or delete the `chrome` folder from the profile.\
For Sidebery: `Help > Reset settings`.

## Customization

* For normal (horizontal) tabs:
    * Remove the line containing `sidebar.css` from file `chrome/userChrome.css`.
* Changing the color scheme:
    * This can be done in `chrome/DownToneUI/_globals.css` by modifying the `--theme` variables.
    * **NOTE** that if vertical tabs are used, these changes have to also be copied to: Sidebery settings > Style editor.

## Notes

* The bookmarks bar inner height varies based on the font you use and maybe other factors. To get the correct height, some trial & error might be needed.
    * First, in `bookmarks.css`, uncomment the line containing `background-color: red` and comment the one below it (`opacity: 0`).
    * Modify the value of `--ui-bookmarks-inner-height` in `chrome/DownToneUI/_globals.css`. (Firefox restart is needed after every change)
        * If the value is too low, the red background will be visible.

        ![example_low_height](assets/example_low_height.png "example_low_height")

        * If the value is too high, the tab bar will be shifted upwards, clipping below the navigation bar.

        ![example_high_height](assets/example_high_height.png "example_high_height")

    * Revert the comments done in the first step.
* To open the sidebar tabs (in case you've gone to History or entered Private Mode): click on the Sidebery extension or use shortcut CTRL+E (shortcut is not working in Windows).

## Credits

* Contributors to the [firefox-csshacks](https://github.com/MrOtherGuy/firefox-csshacks) repository and [Zen Browser](https://zen-browser.app) for some ideas.
* Community on [/r/FirefoxCSS](https://www.reddit.com/r/FirefoxCSS/) for the various snippets of information.
