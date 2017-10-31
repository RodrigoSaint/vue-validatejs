## vue-validatejs

This package is a validation component based on validate.js.
It provides a simple and flexible way to validate and show error messages for individual properties. 

### Usage

Because it relies on validate.js, all examples about validations can be checked at their docs.
To use this component you have to import it into your component.

```javascript

  import VueValidate from 'vue-validate.js'
  
  export default {
    name: 'App',
    components: { VueValidate },

    data () {
      return { model: {}, validation: {name: {presence: {allowEmpty: false}}} }
    }
  }

```

Then in your html create a tag passing the model, the property to validate and the validation

```html
<vue-validate :model="model" :validation="validation" property-name="name"></vue-validate>
```

And that's it. A error message will be generated if the field fail any validation.
