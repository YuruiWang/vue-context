# Attention:

I no longer have the ability or interest in maintaining this package since I am not using Vue in any of my projects
anymore, so I am abandoning `vue-context`. If your project depends on vue-context, please feel free to fork and maintain
the package yourself, or use an [alternative context menu package](#alternatives).

# vue-context

[![npm version](https://img.shields.io/npm/v/vue-context.svg?style=for-the-badge)](https://www.npmjs.com/package/vue-context)
[![npm downloads](https://img.shields.io/npm/dt/vue-context.svg?style=for-the-badge)](https://www.npmjs.com/package/vue-context)
[![GitHub issues](https://img.shields.io/github/issues/rawilk/vue-context.svg?style=for-the-badge)](https://github.com/rawilk/vue-context/issues)
[![GitHub stars](https://img.shields.io/github/stars/rawilk/vue-context.svg?style=for-the-badge)](https://github.com/rawilk/vue-context/stargazers)
[![VueJS version](https://img.shields.io/badge/vue.js-2.x-green.svg?style=for-the-badge)](https://vuejs.org)

`vue-context` provides a simple yet flexible context menu for Vue. It is styled for the standard `<ul>` tag, but any menu template can be used.
The menu is lightweight with its only dependency being `vue-clickaway`. The menu has some basic styles applied to it, but they can be easily 
overridden by your own styles.
<br><br>
The menu disappears when you expect by utilizing `vue-clickaway` and it also optionally disappears when clicked on.

![Screenshot](docs/images/screenshot.jpg)

## Getting Started

The following instructions will help you get the vue-context menu up and running on
your project.

### Installation

Using npm:
```bash
npm i vue-context
```

## Basic Usage

Import the component and use it in your app.

```js
import Vue from 'vue';
import VueContext from 'vue-context';

new Vue({
    components: {
        VueContext
    },
    
    methods: {
        onClick (text) {
            alert(`You clicked ${text}!`);
        }
    }
}).$mount('#app');
```

Next add an element to the page that will trigger the context menu to appear, and also add the context menu to the page.

```html
<div id="app">

    <div>
        <p @contextmenu.prevent="$refs.menu.open">
            Right click on me
        </p>    
    </div>
    
    <vue-context ref="menu">
        <li>
            <a href="#" @click.prevent="onClick($event.target.innerText)">Option 1</a>
        </li>
        <li>
            <a href="#" @click.prevent="onClick($event.target.innerText)">Option 2</a>
        </li>
    </vue-context>
    
</div>
```

> **Notice:** As of version **4.1.0**, the menu styles are not automatically included by default anymore.
> You will need to manually import them now in your own stylesheets.

```bash
@import '~vue-context/dist/css/vue-context.css';

// Or
@import '~vue-context/src/sass/vue-context';
```

## Documentation

For full documentation, go here: https://randallwilk.dev/docs/vue-context.

If you would like to contribute to the documentation, you can edit the docs found here: https://github.com/rawilk/vue-context/tree/master/docs

## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](CONTRIBUTING.md).

- [rawilk](https://github.com/rawilk)
- [wol-soft](https://github.com/wol-soft)
- [nachodd](https://github.com/nachodd)
- [Nberezhnoy](https://github.com/Nberezhnoy)

## Alternatives

- [vue-context-menu](https://github.com/vmaimone/vue-context-menu)
- [@overcoder/vue-context-menu](https://github.com/MicroDroid/vue-context-menu)

See [awesome-vue](https://github.com/vuejs/awesome-vue#context-menu) for other alternatives.

## License

`vue-context` uses the MIT License (MIT). Please see the [license file](https://github.com/rawilk/vue-context/blob/master/LICENSE) for more information.
