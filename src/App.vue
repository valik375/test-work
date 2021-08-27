<template>
  <TheNavbar
      :navbarData="walletValue"
  />
  <router-view/>
</template>

<script>
import TheNavbar from './components/Navbar/TheNavbar.vue'

export default {
  data: () => ({
    walletValue: [
      {
        imagePath: 'coinIcon.png',
        coinValue: '100254',
        coinName: 'Coins',
        buyLink: '/buy-coins',
      },
      {
        imagePath: 'crystalsIcon.png',
        coinValue: '1254',
        coinName: 'Crystals',
        buyLink: '/buy-crystals'
      }
    ]
  }),
  components: {
    TheNavbar
  }
}
</script>
