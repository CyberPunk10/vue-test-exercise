<template>
  <div class="form-group">

    <select
      class="form-control"
      v-if="optionsBrand"
    >
      <option
        v-for="option in optionsBrand" :key="option.id"
        v-bind:value="option.value"
      >{{ option.title }}</option>
    </select>

    <select
      class="form-control"
      v-if="optionsSize">
      <option
        v-for="option in optionsSize" :key="option.id"
        v-bind:value="option.value"
      >{{ option.title }}</option>
    </select>

    <select
      class="form-control"
      v-if="optionsColors">
      <option
        v-for="option in optionsColors" :key="option.id"
        v-bind:value="option.value"
      >{{ option.title }}</option>
    </select>

  </div>
</template>

<script>
export default {
  name: 'Select',
  // data () {
  //   return {
  //     filter: 'brand'
  //   }
  // },
  // watch: {
  //   filter (value) {
  //     console.log(value)
  //   }
  // },
  props: [
    'options-brand',
    'options-size',
    'options-colors'
  ],
  // computed: {
  //   filteredBrands () {
  //     if (this.filter === 'brand') {
  //       console.log(this.filter)
  //       return this.option
  //     }
  //   }
  // },
  methods: {
    hh (el) {
      console.log(this)
    }
  }
}
// console.log()

</script>
