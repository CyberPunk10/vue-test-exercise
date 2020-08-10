<template>
  <div class="form-group">

    <select
      class="form-control"
      v-if="optionsBrand">
      <option
        v-for="option in optionsBrand" :key="option.id"
        v-bind:option="option"
      >{{ option.title }}</option>
    </select>

    <select
      class="form-control"
      v-if="optionsSize">
      <option
        v-for="option in optionsSize" :key="option.id"
        v-bind:option="option"
      >{{ option.title }}</option>
    </select>

    <select
      class="form-control"
      v-if="optionsColors">
      <option
        v-for="option in optionsColors" :key="option.id"
        v-bind:option="option"
      >{{ option.title }}</option>
    </select>

  </div>
</template>

<script>
export default {
  name: 'Select',
  props: [
    'options-brand',
    'options-size',
    'options-colors'
  ],
  methods: {

  }
}
</script>
