#vue-sprinklecompleted
<p>
  <a href="https://www.npmjs.com/package/vue-sprinklecompleted"><img src="https://img.shields.io/npm/v/vue-sprinklecompleted.svg" alt="Version"></a>
  <a href="https://www.npmjs.com/package/vue-sprinklecompleted"><img src="https://img.shields.io/npm/dt/vue-sprinklecompleted.svg" alt="Downloads"></a>
  <a href="https://www.npmjs.com/package/vue-sprinklecompleted"><img src="https://img.shields.io/npm/lvue-sprinklecompleted.svg" alt="License"></a>
</p>

> Creates a spinning completed component for your page!
![](preview.gif)

### Install
#### https://www.npmjs.com/package/vue-sprinklecompleted

### Usage
```js
import VueSprinkleCompleted from 'vue-sprinklecompleted';

export default {
  components: {
	  VueSprinkleCompleted
  },
  ...
}

props: {
			text: {
				type: String,
				default: 'Complete!'
			},
			backgroundColor: {
				type: String,
				default: ' #8b6dfa'
            },
            borderType: {
				type: String,
				default: '2px dashed #8b6dfa'
            },
            textColor: {
				type: String,
                default: 'white'
```


