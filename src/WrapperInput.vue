<template>
  <div class="field">
    <p class="control is-expanded flatpickr" data-wrap="true" data-clickOpens="false" :class="{ [`has-addons-${alignment}`]: alignment }">
      <slot></slot>
      <input class="input" :class="inputClass" type="text" :placeholder="placeholder" :readonly="readonly" v-model="date" data-input/>
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
