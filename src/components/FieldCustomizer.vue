/* eslint-disable */
<template>
  <div v-if="selectedField">
    <h3>Customize Field: {{ selectedField.label }}</h3>
    <div class="field-props">
      <label>Label:</label>
      // eslint-disable-next-line vue/no-mutating-props
      <input v-model="Field" type="text" />
      <!-- Add more customization options as needed -->
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selectedField: Object
  }
};
</script>

<style>
.field-props {
  margin-top: 10px;
}
</style>
