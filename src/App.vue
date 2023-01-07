<script setup>
import vBtn from './components/v-btn.vue'
</script>

<template>
    <v-btn 
      @click="clickBtn"
      :disabled="false"
      :small="false"
      btnIcon="arrow_forward"
      colorBg="primary"
    />
 
</template>


<script>
export default {
  name: 'app',
  components: {
    vBtn
  },
  data() {
    return {}
  },
  methods: {
    clickBtn() {
      console.log('click')
    }
  }
}
</script>