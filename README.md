CKEditor 5 classic editor build
========================================

Note: This is totally same with CKEditor 5 build classic. I only import some neccessary packages and re-use for import to other js file.
You should be use below documentation of CKEditor 5 and know how to use it

## Documentation

See:

* [Installation](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/installation.html) for how to install this package and what it contains.
* [Basic API](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/basic-api.html) for how to create an editor and interact with it.
* [Configuration](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/integration/configuration.html) for how to configure the editor.
* [Creating custom builds](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/development/custom-builds.html) for how to customize the build (configure and rebuild the editor bundle).

## Quick start

- First, install the build from npm:

```bash
npm install --save @ckeditor/ckeditor5-classic
```
- Second, Create `ckeditor.js`:
```javascript
// Or CJS imports:
// ClasicEditor = require('@vantruong1810/ckeditor5-classic');

// Using ES6 imports:
import ClassicEditor from '@vantruong1810/ckeditor5-classic'

// Editor configuration.
ClassicEditor.defaultConfig = {
    toolbar: {
        items: [
            'heading',
            '|',
            'fontFamily',
            'fontSize',
            'alignment',
            'bold',
            'italic',
            'link',
            'bulletedList',
            'numberedList',
            'imageUpload',
            'ckFinder',
            'blockQuote',
            'insertTable',
            'mediaEmbed',
            'undo',
            'redo',
        ]
    },
    image: {
        toolbar: [
            'imageStyle:full',
            'imageStyle:side',
            '|',
            'imageTextAlternative'
        ]
    },
    table: {
        contentToolbar: [
            'tableColumn',
            'tableRow',
            'mergeTableCells'
        ]
    },
    fontFamily: {
        options: [
            'default',
            'Arial, Helvetica, sans-serif',
            'Courier New, Courier, monospace',
            'Georgia, serif',
            'Lucida Sans Unicode, Lucida Grande, sans-serif',
            'Tahoma, Geneva, sans-serif',
            'Times New Roman, Times, serif',
            'Trebuchet MS, Helvetica, sans-serif',
            'Verdana, Geneva, sans-serif'
        ]
    },
    fontSize: {
        options: [
            9,
            11,
            13,
            'default',
            17,
            19,
            21
        ]
    },
    // This value must be kept in sync with the language defined in webpack.config.js.
    language: 'en'
};

// All class editor will be replaced by CKEditor
var allEditors = document.querySelectorAll('.editor');
for (var i = 0; i < allEditors.length; ++i) {
    ClassicEditor
        // Note that you do not have to specify the plugin and toolbar configuration — using defaults from the build.
        .create(allEditors[i])
        .then(editor => {
            console.log('Editor was initialized', editor);
        })
        .catch(error => {
            console.error(error.stack);
        });
}
```

- Finally, import to your main js file:
```javascript
// Using ES6 imports:
import './ckeditor.js';

// Or CJS imports:
require('./ckeditor.js');
```