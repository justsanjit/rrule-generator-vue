<template>
    <div class="container">
        <section class="section">
            <app-form />
        </section>
    </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'app',
  components: {
    AppForm: Form
  }
}
</script>
