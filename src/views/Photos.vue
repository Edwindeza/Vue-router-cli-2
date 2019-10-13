<template>
  <div class="photos">
    <h1>Galería de Fotos</h1>
    <router-link  :to="{name: 'photos', params: { id: item }}"
    v-for="(item, index)  in fotos" :key="index">
      <button>Foto {{item}}</button> 
    </router-link>
    <Foto />
    <button @click="anterior"> Anterior </button>
    <button @click="home"> Home </button>
    <button @click="siguiente"> Siguiente </button>
  </div>
</template>

<script>
import  Foto from "@/components/Photo.vue"

export default {
    components:{
      Foto
    },
    data(){
      return{
        fotos:[1,2,3]
      }
    },
    methods: {
      home(){
        this.$router.push('/')
      },
      anterior(){
        this.$router.go(-1)
      },
      siguiente(){
        this.$router.go(1)
      }
    },
}

</script>