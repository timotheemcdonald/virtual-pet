<script>
// @ is an alias to /src
import {reactive, toRefs} from 'vue'
import DinoPet from '@/components/DinoPet.vue'
import GigaVue from '@/components/GigaVue.vue'

export default {
  name: 'Home',
  components: {
    DinoPet,
    GigaVue
  },
  setup(){
    const state = reactive({
      petName: '',
      userInput: '',
      showCreatePetForm: true,
    })

    const createPet = () => {
      state.petName = state.userInput,
      state.showCreatePetForm = false
    }

    return {
      ...toRefs(state),
      createPet
    }
  }
}
</script>

<template>
  <div class="home">
    <h1>{{ petName}}</h1>
    <section class="wrapper">
    <GigaVue />
    <DinoPet class="dinopet" v-if="petName" />
    </section>
    <form v-if="showCreatePetForm" @submit.prevent>
    <label for="pet-name">Pet Name</label>
    <input type="text" id="pet-name" v-model="userInput" />
    <button @click="createPet">New Pet</button>
    </form>
  </div>
</template>

<style scoped>
.wrapper {
  position: relative;
}

.dinopet {
  max-width: 120px;
  position: absolute;
  left: 700px;
  top: 210px;
}
</style>
