<template>
  <h1>{{ title }}</h1>
  <br />
  <input type="text" ref="name" />
  <button @click="handleClick">Click Me</button>
  <p>Welcome....</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @click="toggleModal"> 
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>New Modal Project Giveaway!..</h1>
      <p>Grab Your Gift From Project!</p>
    </Modal>
  </teleport>
   <teleport to=".modals" v-if="showModalTwo">
    <Modal @click="toggleModalTwo"> 
      <h1>Sign into the news letter!..</h1>
      <p>For updates and promo code</p>
    </Modal>
   </teleport >

  <button @click.alt="toggleModal">Click to Open  Modal</button>
  <button @click.alt="toggleModalTwo">Click to Open  Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App :-)",
      showModal: false,
      showModalTwo:false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
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
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
button {
  background-color: rgba(15, 138, 44, 0.193);
}
</style>
