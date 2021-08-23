<template>
  <TheNavbar
      :navbarData="waletValue"
  />
  <router-view/>
</template>

<script>
import TheNavbar from './components/Navbar/TheNavbar.vue'

export default {
  data: () => ({
    waletValue: [
      {
        imagePath: 'coinIcon.png',
        coinValue: '100 254',
        coinName: 'Coins',
        buyLink: '/buy-coins',
      },
      {
        imagePath: 'crystalsIcon.png',
        coinValue: '1 254',
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
