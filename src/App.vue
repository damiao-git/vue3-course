<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal"> <!-- atributes receive data variables -->
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal2 @close2="toggleModalTwo">
      <template v-slot:potatos>
        <a href="#">Sign 2</a>
        <a href="#">more 2</a>
      </template>
      <h1>Here comes!</h1>
      <p>Toasty!</p>
    </Modal2>
  </div>
  <button @click="toggleModal">openModal</button>
  <button @click="toggleModalTwo">openModalTwo</button>
</template>

<script>

// challenge
//  - create an extra button to open a different modal
//  - use the same modal component but pass in a different template (slot)
//  - use a different method (e.g. toggleModalTwo) and data (e.g. showModalTwo)

import Modal from "./components/Modal.vue";
import Modal2 from "./components/Modal2.vue";

export default {
  name: 'App',
  components:{ Modal, Modal2},
  data(){
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for the Giveamay!',
      text: 'Grab your ninja swag for half price!',
      showModal: false,
      showModal2: false,
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name);
      this.$refs.name.classList.add('active');
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModal2 = !this.showModal2
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
