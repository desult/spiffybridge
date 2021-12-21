# spiffybridge

# Templates:

## intromod

intromod is a template for a modular page. Use the usual YAML front matter. There is a modular template (intro_module.html.twig / intro_module.md) designed to be used for the sub-pages.

### intro_module YAML Front Matter:

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
