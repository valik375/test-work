<template>
  <nav class="navbar">

    <li class="navbar__link">
      <button @click="$router.go(-1)" class="navbar__buttons navbar__buttons_back">
        <img class="navbar__arrow" src="../../assets/images/navbar/backArrow.png" alt="Arrow image">
        <span class="navbar__back-text">Back</span>
      </button>
    </li>
    
    <li class="navbar__link">
      <Donations
        v-for="item in navbarData"
        :key="item.coinName"
        :imagePath="item.imagePath"
        :coinValue="item.coinValue"
        :coinName="item.coinName"
        :buyLink="item.buyLink"
      />
    </li>

    <li class="navbar__link">
      <router-link to="/" class="navbar__buttons navbar__buttons_home">
        <img class="navbar__arrow" src="../../assets/images/navbar/homeIcon.png" alt="Arrow image">
        <span class="navbar__back-text">Home</span>
      </router-link>
    </li>

  </nav>
</template>

<script>
import Donations from './components/Donations.vue'

export default {
  props: ['navbarData'],
  components: {
    Donations
  }
}
</script>

