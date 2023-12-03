<template>
  <section>
    <h3>Я найду тебя!</h3>
    <input type="text"
           :value="inputName"
            @input="inputHandle($event.target.value)"
    >
    <p>{{`Всего имен: ${users.length}, совпадений: ${getFilteredNames.length}`}}</p>
    <ul>
      <li
      v-for="(userName, index) in getFilteredNames"
      :key="index"
      >
        {{userName}}
      </li>
    </ul>
  </section>
</template>

<script>
  export default {
    name: 'UserSearch',
    data(){
      return{
        inputName: '',
        coincidences: 4,
        users: [
            'Василий',
            'Петр',
            'Данил',
            'Григорий'
        ]
      }
    },
    methods: {
      inputHandle(value){
         this.inputName = value
      }
    },
    computed: {
      getFilteredNames(){
        return this.users.filter(name => name.toLowerCase().includes(this.inputName.toLowerCase()))
      }
    }
  }
</script>