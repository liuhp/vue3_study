<template>
  <h2>App</h2>
  <p>msg: {{ msg }}</p>
  <button @click="fn('--')">更新</button>

  <child :msg="msg" msg2="cba" @fn="fn" />
</template>

<script lang="ts">
import { ref } from 'vue'
import child from './components/child.vue'

export default {
  components: {
    child
  },

  setup() {
    const msg = ref('abc')

    function fn(content: string) {
      msg.value += content
    }
    return {
      msg,
      fn
    }
  }
}
</script>