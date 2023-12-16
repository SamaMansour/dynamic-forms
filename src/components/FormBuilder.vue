<template>
  <div class="form-builder">
    <div class="available-fields">
      <draggable :list="availableFields" group="fields">
        <div v-for="field in availableFields" :key="field.type" class="draggable-field">
          {{ field.label }}
        </div>
      </draggable>
    </div>
    <div class="form-canvas">
      <draggable :list="formFields" group="fields">
        <div v-for="field in formFields" :key="field.type" class="form-field">
          {{ field.label }}
          <!-- Additional controls like delete can be added here -->
        </div>
      </draggable>
    </div>
  </div>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  components: {
    draggable
  },
  data() {
    return {
      availableFields: [
        { type: 'text', label: 'Text Field' },
        { type: 'email', label: 'Email Field' },
        // other field types
      ],
      formFields: [] // This will hold the fields added to the form
    };
  }
};
</script>

<style>
.draggable-field, .form-field {
  cursor: pointer;
  margin: 5px;
  padding: 10px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
}
</style>
