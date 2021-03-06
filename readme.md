# copy-text-to-clipboard-async

Copy text to the clipboard in modern browsers

![Travis (.org)](https://img.shields.io/travis/mwiltshire/copy-text-to-clipboard-async?style=flat-square)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

---

This library extends [copy-text-to-clipboard](https://github.com/sindresorhus/copy-text-to-clipboard), adding promise and [Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API) support. If the current browser environment supports the Clipboard API then that will be used, otherwise it will fall back to using `document.execCommand('copy')`.

## Install

```
$ npm install copy-text-to-clipboard-async
```

## Usage

```js
import copy from 'copy-text-to-clipboard-async';

button.addEventListener('click', () => {
  copy('🦄🌈')
    .then(() => console.log('🎉'))
    .catch(() => console.error('😢'));
});
```

## API

### copy(text, options?)

Copy `text` to the clipboard.

Returns a promise that resolves if the text was successfully copied or rejects if the operation failed.

Must be called in response to a user gesture event, like `click` or `keyup`.

#### options

Type: `object`

##### target

Type: `HTMLElement`\
Default: `document.body`

Specify a DOM element where the temporary, behind-the-scenes `textarea` should be appended, in cases where you need to stay within a focus trap, like in a modal.

**Note:** This option will only have an effect if the browser environment does not support the Clipboard API.

## Related

- [copy-text-to-clipboard](https://github.com/sindresorhus/copy-text-to-clipboard) - The original library this is based on
- [clipboardy](https://github.com/sindresorhus/clipboardy) - Access the system clipboard (copy/paste) in Node.js (from the same, original author)
