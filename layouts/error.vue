<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">Ошибка 404</h1>
    <h1 v-else>Что-то пошло не так</h1>
    <nuxt-link to="/">Вернуться на главную</nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Error',
  props: {
    error: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped></style>
