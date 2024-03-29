# mkdocs-link-favicon

The [mkdocs-link-favicon](https://github.com/christophdebaene/mkdocs-link-favicon) plugin enables the automatic generation of a [favicon](https://en.wikipedia.org/wiki/Favicon) before each external link. Additionally, it provides an option to configure externals link to open in a new tab.
A demo can be found on my personal [website](https://christophdebaene.be).

## Installation

To integrate the plugin into your documentation:

 1. Copy the `assets` directory into your `docs` folder.
 2. Add the following lines to your `mkdocs.yml` configuration file:

```yaml
extra_javascript:
    - assets/js/link-favicon.config.js
    - assets/js/link-favicon.js
extra_css:
    - assets/css/link-favicon.css
```

## Configuration

The following providers can be used to generate favicons

 - Google *(default)*
 - DuckDuckGo
 - IconHorse

You can customize icons by adding them to the `assets/icons` directory and specifying a mapping in the configuration file.

The `openInNewWindow` boolean determines whether external hyperlinks should open in a new tab.

Specific URLs for which you don't want a favicon generated, you can include them in the `excludes` array.

Example of the config file `assets/js/link-favicon.config.js`

```javascript
const linkFaviconConfig = 
{
    provider: 'Google',
    openInNewWindow: true,
    iconsPath: '/assets/icons',
    icons: {
        'wikipedia' : 'wikipedia.svg',
        'microsoft' : 'microsoft.svg',
        'github'    : 'github.svg'
    },
    excludes: [
        'https://www.google.com/s2/favicons'
    ],
};
```


