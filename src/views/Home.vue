<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <GigaVue />
  </div>
</template>

<script>
// @ is an alias to /src
import GigaVue from '@/components/GigaVue.vue'

export default {
  name: 'Home',
  components: {
    GigaVue
  }
}
</script>
