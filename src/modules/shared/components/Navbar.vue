<template>
  <div>
<!--       <router-link :to="{ name: 'home' }">Pokemon List</router-link>
      <router-link :to="{ name: 'about' }">About</router-link>
      <router-link :to="{ name: 'pokemon-id', params: { id: 4 } }">Pokemon by ID</router-link> -->
      <CustomLink
        v-for="link in links"
        :key="link.to"
        :link="link" 
      />
  </div>
</template>

<script>
import { defineAsyncComponent } from 'vue';
export default {
    data() {
        return {
            links: [
                { to: 'pokemon-home', name: 'Pokemons' },
                { to: 'pokemon-id', name: 'By ID', id: 4 },
                { to: 'pokemon-about', name: 'Pokemon-About' },

                { to: 'dbz-characters', name: 'Characters' },
                { to: 'dbz-about', name: 'DBZ-About' },

                { to: 'https://google.com', name: 'Google' }
            ]
        }
    },
    components: {
        CustomLink: defineAsyncComponent(() => import('@/modules/shared/components/CustomLink.vue'))
    }
}
</script>

<style scoped>
    div {
        padding: 0 30px;
    }

    div a {
        font-weight: bold;
        margin: 0 10px;
        color:darkolivegreen;
    }

    div .router-link-exact-active {
        color:rgb(46, 199, 41)
    }
</style>