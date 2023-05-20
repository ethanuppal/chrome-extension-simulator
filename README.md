# chrome-extension-simulator

This is a very simple tool that is not close to feature complete for developing popup Chrome extensions outside of Chrome. It provides a simple debugging environment.

![example.png](The chrome extension simulator debugging environment).

## Usage

1. Add [`chrome-simulator.js`](chrome-simulator.js) directly into your project.

2. Take your top-level code and instead call it using `ChromeExtensionSimulator.run`. For example,
    ```js
    // previous
    chrome.tabs.query({active: true, currentWindow: true}, function(tabs) {
        const url = tabs[0].url;
        console.log(url);
    }
    ```

    ```js
    // new
    ChromeExtensionSimulator.run(() => {
        chrome.tabs.query({active: true, currentWindow: true}, function(tabs) {
            const url = tabs[0].url;
            console.log(url);
        }
    });
    ```

3. Place [`index.html`](index.html) in the same directory or in an enclosing directory.

4. Host `index.html` locally by running `make` ([this](Makefile) is the Makefile).

That's it!
