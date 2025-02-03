> A modular UI customization for Firefox, removing borders in the favor of shadows to emphasize the layer elevation.\
> Sidebery is used for the vertical tabs.

![Preview](assets/preview.gif "Preview")

## Install

1. Set Firefox theme to `Dark` in: Firefox settings > Extensions & Themes > Themes.
2. Vertical tabs *(Optional, see [Customization](https://github.com/oviung/DownToneUI-Firefox#Customization))*:
    * Install the [Sidebery extension](https://addons.mozilla.org/en-US/firefox/addon/sidebery/).
    * Go to Sidebery settings (right-click extension) > Help > Import addon data > Choose file `sidebery/settings.json`.
    * *(Optional)* For tab previews: Sidebery settings > Search for "Tabs preview" > Enable and grant permissions.
3. Go to `about:config` (in the URL bar) and set `toolkit.legacyUserProfileCustomizations.stylesheets = true`.
4. Go to `about:support` > Search for "Profile Directory" > Open > Copy the "chrome" folder to this location.
5. Restart Firefox.

## Uninstall

Set `toolkit.legacyUserProfileCustomizations.stylesheets = false` or delete the `chrome` folder from the profile.\
For Sidebery: Sidebery settings > Help > Reset settings.

## Customization

* For normal (horizontal) tabs:
    * In file `chrome/userChrome.css` remove the line `@import "DownToneUI/sidebar.css";`.
* Changing the color scheme:
    * This can be done in `chrome/DownToneUI/_globals.css` by modifying the `--dtui-theme` variables.
    * **NOTE** that if vertical tabs are used, these changes have to also be done in: Sidebery settings > Style editor.
* It's recommended that additional changes or updates of the default styles to be done in files `DownToneUI/override_chrome.css` or `DownToneUI/override_content.css` (which should be created by you). This way, your local changes will persist when this repository is updated.

## Notes

* The bookmarks bar inner height varies based on the font you use and maybe other factors. To get the correct height, some trial & error might be needed.
    * First, in `bookmarks.css`, uncomment the line containing `background-color: red` and comment the one below it (`opacity: 0`).
    * Modify the value of `--dtui-ui-bookmarks-inner-height` in `chrome/DownToneUI/_globals.css`. (Firefox restart is needed after every change)
        * If the value is too low, the red background will be visible.

        ![example_low_height](assets/example_low_height.png "example_low_height")

        * If the value is too high, the tab bar will be shifted upwards, clipping below the navigation bar.

        ![example_high_height](assets/example_high_height.png "example_high_height")

    * Revert the comments done in the first step.
* To open the sidebar tabs (in case you've gone to History or entered Private Mode): click on the Sidebery extension or use shortcut CTRL+E (shortcut is not working in Windows).

## Credits

* Contributors to the [firefox-csshacks](https://github.com/MrOtherGuy/firefox-csshacks) repository and [Zen Browser](https://zen-browser.app) for some ideas.
* Community on [/r/FirefoxCSS](https://www.reddit.com/r/FirefoxCSS/) for the various snippets of information.
