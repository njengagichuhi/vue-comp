<template>
  <h1>{{ title }}</h1>
  <teleport to=".modal" v-if="showModal">
    <Modal theme="sale" @close="togleModal">
      <h1>Johnson Redefined</h1>
      <p>Grab Yourself the feeling</p>
      <template v-slot:name>
        <a href="#">sign up </a>
        <a href="#">more infor</a>
      </template>
    </Modal>
  </teleport>
  <div v-if="showModal2">
    <Modal theme="sale" @close="togleModal2">
      <h1>sign up for a news letter</h1>
      <p>for updates and promocodes</p>
      
    </Modal>
  </div>
  <div><button @click.alt="togleModal">show(alt)</button></div>
  <div>
    <button @click="togleModal2">togleModal2</button>
  </div>

  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My first vue App",
      header: "sign up for the give aways",
      text: "grab yourself a vest",
      showModal: false,
      showModal2: false,
    };
  },

  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("john");
    },
    togleModal() {
      this.showModal = !this.showModal;
    },
    togleModal2() {
      this.showModal2 = !this.showModal2;
    },
  },
};
</script>

<style>
#app ,.moda {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.modal.sale {
  background: crimson;
  color: white;
}
.modal.sale h1 {
  color: white;
}
</style>
