<template>
  <button
      @click="nextPage()"
  type="button">
    next
  </button>
  <button
      @click="clickedPage(page)"
      v-for="page in pages"
      :key="page"
  type="button">
  {{page}}
  </button>
  <button
      @click="prevPage()"
      type="button">
    prev
  </button>
  <p>{{`${currentPage} page of ${pages}`}}</p>
</template>
<script>
  export  default {
    name: 'PaginationButtons',
    data(){
      return{
        pages: 4,
        currentPage: 1
      }
    },
    methods:{
      clickedPage(page){
        return this.currentPage = page
      },
      nextPage(){
        if(this.currentPage !== this.pages) this.currentPage++
      },
      prevPage(){
        if(this.currentPage !== 1) this.currentPage--
      },
      loadUsers(){
        console.log(`Загрузка пользователей страница ${this.currentPage}`)
      }
    },
    watch:{
      currentPage(newValue, oldValue){
        console.log(newValue, 'newValue')
        console.log(oldValue, 'oldValue')
        this.loadUsers(newValue)
      }

    }
  }
</script>