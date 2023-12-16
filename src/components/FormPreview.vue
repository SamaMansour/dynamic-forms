<template>
  <form @submit.prevent="handleSubmit">
    <div v-for="field in formFields" :key="field.type" class="form-field">
      <label :for="field.name">{{ field.label }}</label>
      <input :type="field.type" v-model="field.value" :id="field.name" />
      <!-- Add more input types handling as needed -->
    </div>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  props: {
    formFields: Array
  },
  methods: {
    handleSubmit() {
      // Handle form submission, e.g., emit an event or log the form data
      console.log('Form Data:', this.formFields);
    }
  }
};
</script>

<style>
.form-field {
  margin-bottom: 10px;
}
</style>
