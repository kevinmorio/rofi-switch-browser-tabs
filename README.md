Rofi switch browser tabs
===================

These scripts allow to use [rofi] to switch between tabs in Firefox and Google Chrome / Chromium.


Firefox
---------

#### Dependencies
- Python
- jq

#### Installation
1. Install [MozRepl]
2. Press Alt and go to Tools->MozRepl->Activate on startup
3. Copy `firefox-switch-tabs` and `mozrepl` to a location which is in your path
4. Invoke rofi with `rofi -modi 'firefox:firefox-switch-tabs' -show firefox`

Chrome
----------

#### Dependencies
- Nodejs
- jq

#### Installation
1. `npm install -g chrome-remote-interface`
2. `sudo $EDITOR /usr/bin/chrome-remote-interface` and change `Line 190` from `console.log(display(tabs))` to `console.log(display(JSON.stringify(tabs)))` (this step can be skipped in newer versions of `chrome-remote-interface`)
3. Copy `chrome-switch-tabs` (the file, not the folder) to a location which is in your path
3. Run `google-chrome/chromium --remote-debugging-port=9222`
4. Invoke rofi with `rofi -modi 'chrome:chrome-switch-tabs' -show chrome`

Known bugs
---------------

#### Firefox
Firefox does not load all opened tabs at startup. Unfortunately only loaded tabs can be shown.

[rofi]: https://github.com/davatorium/rofi
[MozRepl]: https://github.com/bard/mozrepl
