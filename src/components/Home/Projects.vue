<template>
  <div class="lg:mt-32 md:mt-0 sm:mt-52 tablet">
    <h1 class="container mx-auto lg:text-left sm:text-center text-5xl mb-20" data-aos="fade-right">
      Derniers projets
    </h1>
    <div class="container mx-auto grid xl:grid-cols-2 md:grid-cols-2 sm:grid-cols-1 gap-x-0 gap-y-24 md:mt-32 sm:-mt-2">
      <div class="mx-auto card" v-for="projet in projets.slice(0, 4)" :key="projet.item" data-aos="fade-up">
        <router-link :to="'projet/'+projet.Slug">
          <img alt="Image illustration projet" class="img-fluid" :src="projet.Image[0].formats.medium.url">
          <div class="p-5">
            <h2 class="xl:text-2xl md:text-base sm:text-l mt-1 textSize">{{projet.Titre}}</h2>
            <h3 class="xl:text-sm sm:text-xs text-blue-300 font-bold mt-2">{{projet.type.Type}}</h3>
          </div>
        </router-link>
      </div>
    </div>
    <div class="grid grid-cols-1 mt-28" data-aos="fade-up">
      <div class="mx-auto">
        <p class="text-center text-sm mb-4 text-gray-500">et plus ...</p>
        <router-link class="btn text-white font-bold py-2 px-4 rounded-full" tag="button" to="/portfolio">Découvrir tous mes projets</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['projets']),
  },  
}
</script>

<style scoped>
.card {
  background: #202020;
  border-radius: 20px;
  width: 70%;
  height: 100%;
}

.card img {
  margin: auto;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}

.btn:hover {
  background: #202020;
  color: #93C5FD;
}

.btn:focus {
  outline: unset;
}

.btn {
  transition: .5s;
  color: #202020;
  background: #93C5FD;
}

@media screen and (max-width: 640px) {
  .card {
    width: 90%;
  }
}

@media screen and (max-width: 1300px) and (min-width: 1000px) {
  .textSize {
    font-size: 18px;
  }
}
</style>