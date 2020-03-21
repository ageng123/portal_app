<template>
  <div>
    <LoginForm />
  </div>
</template>
<script>
import LoginForm from '~/components/Form/form.vue'
export default {
  namespaces: true,
  components: {
    LoginForm
  },
  layout: 'LayoutPortal'
}
</script>
<style>
</style>
