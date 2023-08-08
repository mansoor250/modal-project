<template>
 <h1>{{ title }}</h1><br>
 <input type="text" ref="name">
 <button @click="handleClick"> Click Me</button>
 <p>Welcome....</p>
 <div v-if="showModal">
  <Modal :header='header' :text='text' theme ='sale' @click="toggleModal"/> 
 </div>
 <button @click="toggleModal">Open Modal</button>
</template>

<script> 
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{ Modal },
 data(){
  return{
     title: 'My First Vue App :-)',
     header: "Sign up for Giveaway!",
     text:'Sign in to your account!' ,
     showModal:false

  }
 },
 methods: {
  handleClick(){
    console.log (this.$refs.name)
    this.$refs.name.classList.add('active')
    this.$refs.name.focus()
  },
  toggleModal() {
    this.showModal=!this.showModal
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
button{
  background-color: rgba(15, 138, 44, 0.193);
}
</style>
