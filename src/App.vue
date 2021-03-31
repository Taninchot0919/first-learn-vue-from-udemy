<template>
    <h1>{{title}}</h1>
    <input type="text" ref="name">
    <button @click="handleClick">Click Me</button>
    <Modal />
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name:'App',
  components:{ Modal },
  data() {
    return {
      title: 'This is my First App'
    }
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name.value)
      this.$refs.name.classList.add('active')
    }
  },

}
</script>

<style>
#app{
  margin: 0;
}
</style>
