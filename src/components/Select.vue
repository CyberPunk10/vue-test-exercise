<template>
  <div class="form-group">
    <select class="form-control">
        <option>{{ options[0].title }}</option>
        <option>{{ options[1].title }}</option>
        <option>{{ options[2].title }}</option>
        <option>{{ options[3].title }}</option>
        <option>{{ options[4].title }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Select',
  props: ['options'],
  methods: {

  }
}
</script>
