<script>
import { defineAsyncComponent } from 'vue';

export default {
  name: 'TheWelcome',
  components: {
    BigYellowUserName: defineAsyncComponent(() => import('./BigYellowUserName.vue'))
  },
  props: {
    msg: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      showUserName: false
    }
  },
}
</script>

<template>
  <div class="greetings">
    <h1 class="username">{{ msg }}</h1>
    <button id="toogleShowUserName" @click="showUserName = !showUserName">Toggle User Name</button>
    <div v-if="showUserName">
      <BigYellowUserName username="Welcome Vue Master Ian!" />
    </div>

  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
