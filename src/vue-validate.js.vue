<template>
  <span class="error-message" v-if="errorMessageCollection && errorMessageCollection.length">
      {{errorMessageCollection[0]}}
  </span>
</template>
<script>

var validate = require('validate.js');

function reduceObject(property, input) 
{
    var smallObject = {};
    smallObject[property] = input[property];
    return smallObject;
}

export default 
{
    props: ['propertyName', 'model', 'validation'],
    computed: 
    {
        errorMessageCollection ()
        {
            var fieldValidation = reduceObject(this.propertyName, this.validation);
            return validate(this.model, fieldValidation, {format: 'flat'});
        }
    }
}
</script>
