<template>
  <section class="container">
    <date-picker-from-to :label="label" :from_dt.sync="from" :to_dt.sync="to"/>
    <span>from: {{from}} to: {{to}}</span>
  </section>
</template>

<style lang="scss" scoped>
</style>

<script>
import DatePickerFromTo from '../src/vue-mg-date-picker-from-to'
export default {
  data() {
    return {
      label: 'ラベル',
      from: '',
      to: '',
    }
  },
    methods: {
      ///
    },
  components: {
    DatePickerFromTo,
  },  
}
</script>