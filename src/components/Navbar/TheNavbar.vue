<template>
  <nav class="navbar">

    <ul class="navbar__container">
      <li class="navbar__link">
        <a @click="$router.go(-1)" class="navbar__buttons navbar__buttons_back">
          <img class="navbar__arrow" src="../../assets/images/navbar/backArrow.svg" alt="Arrow image">
          <span class="navbar__button-text">Back</span>
        </a>
      </li>

      <li class="navbar__wallets">
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
          <img class="navbar__arrow" src="../../assets/images/navbar/homeIcon.svg" alt="Home image">
          <span class="navbar__button-text">Home</span>
        </router-link>
      </li>
    </ul>

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


