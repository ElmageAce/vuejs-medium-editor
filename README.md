[![npm version](https://badge.fury.io/js/vuejs-medium-editor.svg)](https://github.com/manuelgeek/vuejs-medium-editor)  [![npm version](https://badgen.net/npm/dt/vuejs-medium-editor)](https://github.com/manuelgeek/vuejs-medium-editor) [![npm version](https://badgen.net/npm/license/lodash)](https://github.com/manuelgeek/vuejs-medium-editor)
# VueJS Medium Editor

Vue Js component for Medium Editor wrapper with https://github.com/yabwe/medium-editor
But all plugins are re-writing in Vue.js
All Medium Editor configs are supported

## Demo
[Demo](https://manuelgeek.github.io/vuejs-medium-editor/)

## Features
- Medium like editor
- Image uploader and description
    - Image width configable width for normal / expand / full screen sizing
    - Imgur uploading 
- Embed Gist
- Inline code syntax highting

## Usage

### Installation

```
yarn add vuejs-medium-editor
```
OR 

```
npm install vuejs-medium-editor
```

### Usage

add to global component

```js
import Vue from 'vue'
import MediumEditor from 'vuejs-medium-editor'

Vue.component('medium-editor', MediumEditor)
```

Don't forget to include css file in your project
```js
require 'medium-editor/dist/css/medium-editor.css'
require 'vuejs-medium-editor/src/themes/default.css'
// for the code highlighting
require 'highlight.js/styles/ocean.css';
```
OR in `styles` like below

```css
<style lang="css">
@import "~medium-editor/dist/css/medium-editor.css";
@import "./themes/default.css";
/*@import '~highlight.js/styles/github.css';*/
@import '~highlight.js/styles/ocean.css';
</style>
```

usage

```js
<medium-editor :content='content' :options='options' />

<script>
export default {
    data() {
        return {
            content: "",
            options: {
            }
        }
    }
}
</script>
```
### toolbar
you can customize the toolbar buttons too 

```js
    toolbar: {
          buttons: ["bold", "italic", "underline", "quote", "h1", "h2", "h3", 'pre', 'unorderedlist']
        }
```
available options: All options are available [here](https://github.com/yabwe/medium-editor#mediumeditor-options)
You can also override options like in Medium Editor ;
 ```js
 buttons: ["anchor", {
                       name: 'pre',
                       action: 'append-pre',
                       aria: 'code highlight',
                       tagNames: ['pre'],
                       contentDefault: '<b><\\></b>',
                       contentFA: '<i class="fa fa-code fa-lg"></i>'
                   },]

 ```

### images

available options too thanks to [ErgoFriend](https://github.com/ErgoFriend) pull request on the original repo

```js
options: {
    uploadUrl: "https://api.imgur.com/3/image",
    uploadUrlHeader: {'Authorization': 'Client-ID a3tw6ve4wss3c'},
    file_input_name: "image",
    imgur: true,
 }

```

### code highlighting
Code highlighting is inbuilt using [highlight.js](https://github.com/highlightjs/highlight.js)

You should include the `highligh.js` css file within the styles
```css
<style>
    /*default css  */
    @import '~highlight.js/styles/default.css';
    /* github style */
    @import '~highlight.js/styles/github.css';
</style>
```

You can get [more theme styles here](https://highlightjs.org/static/demo/)


### Nuxt.js Usage

create a plugins

```js
import Vue from 'vue'
import MediumEditor from 'vuejs-medium-editor'

Vue.component('medium-editor', MediumEditor)
```

import a plugin in nuxt.config.js with disable ssr mode

```js
plugins: [
    { src: '~/plugins/medium-editor', ssr: false },
]
```

include a css file
```js
css: [
    'medium-editor/dist/css/medium-editor.css',
    'vuejs-medium-editor/src/themes/default.css',
    'highlight.js/styles/ocean.css' //if using code highlight
]
```

## About Me 

<p align="center"><img src="https://magak.me/assets/images/Geek-logo.png" width="150">

<a target="_blank" href="https://magak.me">Magak Emmanuel</a>
</p>

## Credits

The original repo [vue2-medium-editor](https://github.com/tui2tone/vue2-medium-editor)
customised this to my preference

[<img width=200 src="https://appslab.co.ke/assets/img/logo.png">](https://appslab.co.ke) 

## License

[MIT](LICENSE)

[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=for-the-badge)](#)

[![Open Source Love](https://badges.frapsoft.com/os/v2/open-source-200x33.png?v=103)](#)


Happy coding, Star before Fork 😊💪💯
