<template>
  <div class="form-group">

    <select
      class="form-control"
      v-if="optionsBrand"
      v-model="filterBrand"
    >

      <option
        v-for="option in optionsBrand" :key="option.id"
        v-bind:value="option.title"
      >{{ option.title }}</option>

    </select>

    <select
      class="form-control"
      v-if="optionsSize"
      v-model="filterSize"
      >

      <option
        v-for="option in optionsSize" :key="option.id"
        v-bind:value="option.title"
      >{{ option.title }}</option>

    </select>

    <select
      class="form-control"
      v-if="optionsColor"
      v-model="filterColor"
      >

      <option
        v-for="option in optionsColor" :key="option.id"
        v-bind:value="option.title"
      >{{ option.title }}</option>

    </select>

  </div>
</template>

<script>
export default {
  name: 'Select',
  data () {
    return {
      filterBrand: 'Бренд',
      filterSize: 'Размер',
      filterColor: 'Цвет'
    }
  },
  props: [
    'options-brand',
    'options-size',
    'options-color'
  ],
  watch: {
    filterBrand (value) {
      this.$emit('push-filter-brand', value)
    },
    filterSize (value) {
      this.$emit('push-filter-size', value)
    },
    filterColor (value) {
      this.$emit('push-filter-color', value)
    }
  },
  methods: {

  }
}

</script>
