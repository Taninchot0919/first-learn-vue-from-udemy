<template>
  <h1>{{ title }}</h1>
  <!-- For Example handleClick -->
  <!-- <input type="text" ref="name">
    <button @click="handleClick">Click Me</button> -->
  <p>Welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <!-- It can use v-slot at first because when link in Modal.vue it will down -->
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaways</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <!-- It can use v-slot at first because when link in Modal.vue it will down -->
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promos codes!</p>
    </Modal>
  </teleport>

  <button @click.alt="toggleModal">
    Open Modal (alt in window , option in mac)
  </button>

  <button @click="toggleModalTwo">
    Open Modal
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "This is my First App",
      // header: "Sign up for the Giveaways",
      // text: "Grab your ninja swag for half price!",
      showModal: false,
      showModalTwo: false
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
    // handleClick(){
    //   console.log(this.$refs.name.value)
    //   this.$refs.name.classList.add('active')
    // },
  }
};
</script>

<style>
#app , #modals {
  font-family: Avenir, Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
