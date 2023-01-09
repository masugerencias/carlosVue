<template>
  <v-app>
    <v-main>
      <UserProfile></UserProfile>
      <PokeList>
<!--         <template #contenido="item"> {{item.item.nombre}}</template>

 -->        
 <template #contenido="{item}"> {{item.nombre}}</template>

 
 <template #titulo > 
          <h2>Primera renderización titulo</h2>
        </template>
        <template #subtitulo>
          Segunda renderizacion sutbtitulo
        </template>

      </PokeList>
      <PokeList>
        <template #contenido="item"> {{item.item.habilidad}}</template>

      </PokeList>
    </v-main>
  </v-app>
</template>

<script>
import PokeList from './components/PokeList.vue'
import UserProfile from './components/UserProfile.vue'
export default {
  name: 'App',

  components: {
    PokeList, UserProfile
  },

  data() {
    return {

    }
  },
};
</script>
