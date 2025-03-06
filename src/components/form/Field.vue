<script lang="ts" setup>

import { useField } from 'vee-validate'
import { StringSchema } from 'yup';

interface Props {
  label: string
  type: 'text' | 'email' | 'tel' | 'number'
  name: string
  placeholder: string
  validator?: StringSchema<string> | undefined 
}

const props = withDefaults(defineProps<Props>(), {
  validator: undefined
})


const { value, errorMessage } = useField(props.name, props.validator);

</script>

<template>
  <div class="field-wrapper">
    <label class="form-field">
      {{ props.label }}
      <input 
      v-model="value"
      :name="props.name"
      :type="props.type"
      :placeholder="props.placeholder"
    />
    </label>
    <div v-if="errorMessage" class="form-field__error">
      {{ errorMessage }}
    </div>
  </div>
  
</template>

<style scoped>

.field-wrapper {
  position: relative;
}

.form-field {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.form-field__error {
  position: absolute;
  transform: translateY(100%);
  left: 5px;
  bottom: -5px;
  color: red;
  font-size: 13px;
  font-weight: 500;
  line-height: 1;
}


</style>
