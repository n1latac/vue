<template>
  <h1>
  {{getFullName}}
  </h1>
  <ul>
    <li
    v-for="(user, index) in users"
    :key="index"
    >
      {{`${index} ${user.firstName} ${user.lastName}`}}
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'UserCard',
    data(){
      return {
        firstName: 'John',
        secondName: 'Edgar',
        lastName: 'Doe',
        users: [
          {
            firstName: 'Ivan',
            lastName: 'Ivanovich'
          },
          {
            firstName: 'Pasha',
            lastName: 'Pashovich'
          },
          {
            firstName: 'Oleg',
            lastName: 'Olegovich'
          }
        ]
      }
    },
    computed: {
      getFullName(){
        return this.firstName + ' ' + this.secondName + ' ' + this.lastName
      }
    }
  }
</script>