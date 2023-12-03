<template>
  <div class="root">
    <label>
      Введите email:
      <input type="email" v-bind:value="email" v-on:input="emailInput($event.target.value)">
      <input type="password" :value="password" @input="passwordInput($event.target.value)">
    </label>
    <div>
      <button @click="decreaseCount">-</button>
      <input type="number" :value="count" max="10" min="1" @change="arrowsChange($event.target.valueAsNumber)">
      <button @click="increaseCount">+</button>
    </div>
    <UserCard/>
    <Pagination/>
  </div>
</template>

<script>
import Pagination from "@/components/Pagination.vue";
import UserCard from "@/components/UserCard.vue";
  export default {
    name: 'MyComponent',
    components:{
      Pagination,
      UserCard
    },
    data() {
      return {
        email: 'example@mail.com',
        password: '123456',
        count: 5
      }
    },
    methods: {
      emailInput(value){
        this.email = value
      },
      passwordInput(value){
        this.password = value
      },
      increaseCount(){
        if(this.count !== 10){
          this.count++
        }
      },
      decreaseCount(){
        if(this.count !== 1){
          this.count--
        }
      },
    },

  }
</script>