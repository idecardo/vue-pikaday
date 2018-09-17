# vue-pikaday

A [Pikaday](https://github.com/dbushell/Pikaday/) wrapper for [Vue.js 2](https://vuejs.org/).

### Installation

```
npm install --save @idecardo/vue-pikaday
```

### Usage

```javascript
import Pikaday from '@idecardo/vue-pikaday'

// Import your preferred pikaday style/theme.
import 'pikaday/css/pikaday.css'

export default {
    components: {
        Pikaday,
    },

    data: () => ({
        date: '2018-10-05',

        settings: {
            firstDay: 3,
        },
    }),
}
```

#### Basic

```html
<pikaday v-model="date"></pikaday>
```

#### Settings

```html
<pikaday v-model="date" :settings="settings"></pikaday>
```

#### Theme

```scss
// You can also import your preferred style/theme in your main SASS file or your component's <style lang="scss"/> section.

@import "~pikaday/scss/pikaday.scss";
```
