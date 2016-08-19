# <tc-analytics\>


### TCBehaviors.GoogleAnalyticsBehavior

Behavior for interacting with Google Analytics. Use `virtualPageView` for
   sending page views from internal pages. Use `trackEvent` for tracking
   individual events.


Sample usage:

    <dom-module id="x-app">
      <template>
        <!-- This should only be imported once, when initiating the app -->
        <tc-google-analytics></tc-google-analytics>

        <!-- track an event via an event listener -->
        <paper-button on-tap="_registerEvent"></paper-button>

        <!-- track an event using a method from the behavior, using data-* attributes. -->
        <paper-button on-tap="trackEventFromDataAttrs" data-category="paper-button" data-action="tap" data-label="button 2"></aper-button>
      
      </template>
      <script>
        Polymer({
          is: "x-app",
 
          behaviors: [
            TCBehaviors.GoogleAnalyticsBehavior
          ],
 
          properties: {
            apiBaseUrl: {
              type: String,
              value: '/api/i18n/'
            }
          },

          ready: function() {
            // Track a page
            this.virtualPageView('/home');
          }
 
          _registerEvent: function(e) {
            this._trackEvent('paper-button', 'clicked', 'button 1');
          }
        });
      </script>
    </dom-module>


### TCBehaviors.TagManagerBehavior

Behavior for interacting with Google Tag Manager. Use `virtualPageView` for
   sending page views from internal pages. Use `trackEvent` for tracking
   individual events.


Sample usage:

    <dom-module id="x-app">
      <template>
        <!-- This should only be imported once, when initiating the app -->
        <tc-tag-manager></tc-tag-manager>

        <!-- track an event via an event listener -->
        <paper-button on-tap="_registerEvent"></paper-button>

        <!-- track an event using a method from the behavior, using data-* attributes. -->
        <paper-button on-tap="trackEventFromDataAttrs" data-category="paper-button" data-action="tap" data-label="button 2"></aper-button>
      
      </template>
      <script>
        Polymer({
          is: "x-app",
 
          behaviors: [
            TCBehaviors.TagManagerBehavior
          ],

          ready: function() {
            // Track a page
            this.virtualPageView('/home');
          }
 
          _registerEvent: function(e) {
            this.trackEvent('paper-button', 'clicked', 'button 1');
          }
        });
      &lt;/script>
    </dom-module>


## Install the Polymer-CLI

First, make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve your application locally.

## Viewing Your Application

```
$ polymer serve
```

## Building Your Application

```
$ polymer build
```

This will create a `build/` folder with `bundled/` and `unbundled/` sub-folders
containing a bundled (Vulcanized) and unbundled builds, both run through HTML,
CSS, and JS optimizers.

You can serve the built versions by giving `polymer serve` a folder to serve
from:

```
$ polymer serve build/bundled
```

## Running Tests

```
$ polymer test
```

Your application is already set up to be tested via [web-component-tester](https://github.com/Polymer/web-component-tester). Run `polymer test` to run your application's test suite locally.
