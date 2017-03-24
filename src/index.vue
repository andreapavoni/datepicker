<template>
  <component v-model="date" :placeholder="placeholder" :inputClass="inputClass" :is="wrap ? 'WrapperInput' : 'SingleInput'">
    <slot></slot>
  </component>
</template>

<script>
import Flatpickr from 'flatpickr'
import BaseInput from './BaseInput'
import SingleInput from './SingleInput'
import WrapperInput from './WrapperInput'


function Datepicker (selector, config) {
  if (config.locale) {
    Flatpickr.l10ns[`${config.locale}`] = require(`../../flatpickr/dist/l10n/${config.locale}.js`)[`${config.locale}`]
    Flatpickr.localize(Flatpickr.l10ns[`${config.locale}`]);
  }

  return Flatpickr.call(this, selector, config)
}

Datepicker.prototype = Flatpickr.prototype

export default {
  mixins: [BaseInput],

  components: {
    SingleInput,
    WrapperInput
  },

  data () {
    return {
      datepicker: null
    }
  },

  mounted () {
    if (!this.datepicker) {
      this.datepicker = new Datepicker(this.$el, this.config)
      this.popupItem = this.datepicker.calendarContainer
    }
  },

  beforeDestroy () {
    if (this.datepicker && !this.static) {
      this.datepicker.destroy()
      this.datepicker = null
    }
  },

  computed: {
    wrap () {
      return !!this.config.wrap
    },
    static () {
      return !!this.config.static
    },
    name () {
      return this.wrap ? 'wrapperInput' : 'singleInput'
    }
  }
}
</script>

<style lang="stylus">
$calendar_background = #ffffff
$calendar_border_color = #d3d6db

$months_color = #111
$months_background = transparent

$weekdays_background = transparent

$day_text_color = #222324
$day_hover_background_color = #d3d6db

$today_color = #ed6c63
$selected_day_background = #1fc8db

@import '~flatpickr/src/style/flatpickr'

.flatpickr-calendar.hasWeeks
  width: auto !important
</style>
