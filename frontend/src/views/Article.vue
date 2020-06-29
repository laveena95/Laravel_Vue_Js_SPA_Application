<template>
  <div>
      <div v-for="item in article" :key="item.id">
          <h1>{{ item.title }}</h1>
          <p>{{ item.body }}</p>
      </div>
      <h2>bhcfxcghj</h2>
  </div>
</template>

<script>
import axios from 'axios'

export default {
    name:'article',
    data(){
        return{
            articles: null
        }     
    },
    created(){
        this.getArticles()
    },
    methods: {
        getArticles(){
            axios
                .get('/api/articles')
                .then(res=>{
                    const{data:{data}} = res
                    this.arcticles = data
                    console.log(res)
                })
                .catch(err =>{console.log(err)})
        }
    }
}
</script>

<style>

</style>
