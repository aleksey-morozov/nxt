<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-demo
      </h1>
      <h2 class="subtitle">
        My divine Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link to="/catalog" class="button--green">Каталог</nuxt-link>
        <nuxt-link to="/about" class="button--green">О компании</nuxt-link>
      </div>

      <button class="btn btn-primary" @click="visible = !visible"> Показать </button>
      <transition name="my-animation">
        <div v-if="visible" class="content">
          <h1>Это какой-то заголовок</h1>
          <p>Это какой-то текст</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      visible: 0,
    }
  },
}
</script>

<style>
.my-animation-enter-active {
  animation: 1s hide reverse;
}
/*.my-animation-enter {
  opacity: 0;
  border: 1px solid red;
}
.my-animation-enter-to {
  border: 5px solid green;
}*/
.my-animation-leave-active {
  animation: hide 3s;
}
.my-animation-leave-to {
}
@keyframes hide {
  0% { opacity: 0.5; }
  20% { opacity: 0.5; transform: scale(1.5); }
  100% { opacity: 0.5; transform: scale(0.1); }
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
