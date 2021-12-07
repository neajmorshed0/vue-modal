<template>
  <h3>{{ title }}</h3>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </Modal>
  </teleport>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:para>
        <p>Lorem ipsum dolor sit amet.</p>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Open modal(alt)</button>
  <button @click="toggleModalTwo">Open modaltwo</button>
</template>

<script>
import Modal from './components/Modal';
export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      title: 'Vue app',
      header: 'Ninja givaway',
      text: 'grab your price',
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
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
</style>
