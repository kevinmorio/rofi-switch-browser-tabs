Rofi switch browser tabs
===================

These scripts allow to use [rofi] to switch between tabs in Firefox and Google Chrome / Chromium.


Firefox
---------

####Dependencies
- Python
- jq

####Installation
1. Install [MozRepl]
2. Press Alt and go to Tools->MozRepl->Activate on startup
3. Copy `firefox-switch-tabs` and `mozrepl` to a location which is in your path
4. Invoke rofi with `rofi -modi 'firefox:firefox-switch-tabs' -show firefox`

Chrome
----------

####Dependencies
- Nodejs
- jq

####Installation
1. `npm install -g chrome-remote-interface`
2. `sudo $EDITOR /usr/bin/chrome-remote-interface` and change `Line 190` from `console.log(display(tabs))` to `console.log(display(JSON.stringify(tabs)))`
3. Copy `chrome-switch-tabs` to a location which is in your path
3. Run `google-chrome/chromium --remote-debugging-port=9222`
4. Invoke rofi with `rofi -modi 'chrome:chrome-switch-tabs' -show chrome`

Known bugs
---------------

####Firefox
Firefox does not load all opened tabs at startup. Unfortunately only loaded tabs can be shown.

[rofi]: https://davedavenport.github.io/rofi/
[MozRepl]: https://addons.mozilla.org/en-US/firefox/addon/mozrepl/
