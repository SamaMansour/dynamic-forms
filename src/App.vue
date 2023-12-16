<template>
  <div id="app">
    <header>
      <h1>Vue Dynamic Form Builder</h1>
    </header>
    <main>
      <section class="form-builder-section">
        <FormBuilder @update-form="updateForm" />
      </section>
      <aside class="field-customizer-section" v-if="selectedField">
        <FieldCustomizer :selectedField="selectedField" @update-field="updateField" />
      </aside>
      <section class="form-preview-section">
        <FormPreview :formFields="formFields" />
      </section>
    </main>
  </div>
</template>

<script>
import FormBuilder from './components/FormBuilder.vue';
import FieldCustomizer from './components/FieldCustomizer.vue';
import FormPreview from './components/FormPreview.vue';

export default {
  name: 'App',
  components: {
    FormBuilder,
    FieldCustomizer,
    FormPreview
  },
  data() {
    return {
      selectedField: null,
      formFields: []
    };
  },
  methods: {
    updateForm(selectedField) {
      this.selectedField = selectedField;
    },
    updateField(updatedField) {
      // Find the field in formFields and update it
      const index = this.formFields.findIndex(field => field.name === updatedField.name);
      if (index !== -1) {
        this.$set(this.formFields, index, updatedField);
      }
    }
  }
};
</script>

<style>
/* ... existing styles ... */
</style>
