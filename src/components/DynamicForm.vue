<template>
  <form @submit.prevent="handleSubmit">
    <div v-for="(field, index) in formFields" :key="index" class="form-group">
      <label :for="field.name">{{ field.label }}</label>
      <input 
        :type="field.type" 
        v-model="field.value" 
        :id="field.name" 
        :placeholder="field.placeholder" 
        :name="field.name" 
      />
      <!-- Placeholder for potential validation message -->
      <span v-if="field.validationError" class="error-message">{{ field.validationError }}</span>
    </div>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  name: 'DynamicForm',
  data() {
    return {
      formFields: [
        {
          name: 'name', 
          label: 'Name', 
          type: 'text', 
          value: '', 
          placeholder: 'Enter your name'
        },
        {
          name: 'email', 
          label: 'Email', 
          type: 'email', 
          value: '', 
          placeholder: 'Enter your email'
        },
        {
          name: 'message', 
          label: 'Message', 
          type: 'textarea', 
          value: '', 
          placeholder: 'Enter your message'
        }
        // Add more fields as needed
      ]
    };
  },
  // other component options like methods, computed, etc.
};
</script>

<style scoped>
.form-group {
  margin-bottom: 15px;
}

.error-message {
  color: red;
  font-size: 0.8em;
}
</style>
