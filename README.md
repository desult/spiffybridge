# spiffybridge

## Templates:

### intromod

intromod is a template for a modular page. Use the usual YAML front matter. There is a modular template (intro_module.html.twig / intro_module.md) designed to be used for the sub-pages.

#### intro_module YAML Front Matter:

```
bgcolor: white
bgimage: image.jpg
layout:
  - image: image.png
    align: center
  - cardcolor: white
    text: String here is formatted as an h2 header
    textcolor: '#454b54'
  - cardcolor: white
    text: String here is formatted as an h2 header
    textcolor: '#454b54'
  - cardcolor: white
    longtext: String here is formatted as a p paragraph
    textcolor: '#454b54'
```

## Theme Inheritance

Spiffy Bridge is designed with theme Inheritance in mind. A sub-theme can be created that takes advantage of the variables in the SCSS. SCSS variables can change the color scheme. It is recommended that a sub-theme be created so that any future updates to the theme do not over-write the changes.

### Creating a Sub-Theme

1. Create a new empty folder in the themes folder next to spiffybridge and give it a name.
2. Copy blueprints.yaml from spiffybridge.
3. copy spiffybridge.yaml and rename it to have new theme name.

Add this to newtheme.yaml:

```
streams:
 schemes:
   theme:
     type: ReadOnlyStream
     prefixes:
       '':
         - user/themes/spiffybridge-orange
         - user/themes/spiffybridge
```

4. Create a scss folder in the new theme directory.

In scss folder create _custom.scss and add:

```
body {
  background-image: url("../../spiffybridge/images/bgstripesthingrey2.svg"), linear-gradient(to right, hsl($hue01, $saturation01, 35%), hsl($hue01, $saturation01, 48%));
 }
```

Copy _fonts.scss from spiffybridge and edit it to:

```
@font-face {
    font-family: 'oswald_regularregular';
    src: url('../../spiffybridge/fonts/oswald/oswald-regular-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal; }

@font-face {
    font-family: 'cornerstoneregular';
    src: url('../../spiffybridge/fonts/cornerstone/cornerstone-webfont.woff2') format('woff2'),
         url('../../spiffybridge/fonts/cornerstone/cornerstone-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}
```

Copy _variables.scss from spiffybridge. All values here are designed to be edited.

Create styles.scss. The file's contents should be as follows:

```
@import 'variables';
@import 'fonts';
@import '../../spiffybridge/scss/main';
@import '../../spiffybridge/scss/nav';
@import '../../spiffybridge/scss/intro';
@import 'custom';
```
