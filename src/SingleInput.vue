<template>
  <div class="field">
    <p class="control is-expanded">
      <input class="input" :class="inputClass" type="text" :placeholder="placeholder" :readonly="readonly" v-model="date"/>
    </p>
  </div>
</template>

<script>
import BaseInput from './BaseInput'

export default {
  mixins: [BaseInput],

  props: {
    readonly: Boolean
  }
}
</script>
