# Plant UML IMG GitBook Plugin

[![Build Status](https://travis-ci.org/vboulaye/gitbook-plugin-local-plantuml-img.svg?branch=master)](https://travis-ci.org/vboulaye/gitbook-plugin-local-plantuml-img)

This plugin builds on the [local-plantuml](https://plugins.gitbook.com/plugin/local-plantuml) plugin.

It uses a local plantuml java call to generate the images.

In addition to the standard block plugin call, the plugin processes the img whose src is a .puml file. 
This allows setting an alt/title attribute and using plugins such as [image-captions](https://github.com/todvora/gitbook-plugin-image-captions) for plantuml generated files.
This way you can also use a plugin to edit the plantuml file separately.

example, with a Markdown text:

```markdown
    [alt text](diagram.puml "title text")
```
    
The plugin will read the file diagram.puml relative to the .md page, transform it into svg (for html) or png (for ebooks) and replace the src attribute with the generated image location.

```html
    <img src='diagram.svg' alt="alt text' title='title text' />
```
 
 
# Release Notes
`1.0.0` Initial release with support of img tags.

# Issues
* Currently a new java process is started for every `plantuml` block in your markdown files. This can be a little slow.
