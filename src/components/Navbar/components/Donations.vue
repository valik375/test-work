<template>
  <div @click="changeValue(coinValue)" class="wallets">
    <img :src="require(`@/assets/images/navbar/${imagePath}`)" :alt="coinName" class="wallets__image">
    <div class="wallets__content">
      <span class="wallets__value">{{coinsValue}}</span>
      <span class="wallets__coin-name">{{coinName}}</span>
    </div>
    <div class="wallets__button-wrapper"  >
      <router-link :to="buyLink" class="wallets__button">
        <svg class="wallets__plus-icon" width="13" height="13" viewBox="0 0 13 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M8 0H5V5H0V8H5V13H8V8H13V5H8V0Z" fill="url(#paint0_linear)"/>
          <defs>
            <linearGradient id="paint0_linear" x1="6.5" y1="0" x2="6.5" y2="13" gradientUnits="userSpaceOnUse">
              <stop stop-color="#B1FFAF"/>
              <stop offset="1" stop-color="white"/>
            </linearGradient>
          </defs>
        </svg>
      </router-link>
      <div class="wallets__button-bg"></div>
    </div>
  </div>
</template>

<script>

export default {
  props: ['imagePath', 'coinValue', 'coinName', 'buyLink'],
  data: () => ({
    userWidth: window.innerWidth,
    coinsValue: null,
  }),
  mounted() {
    window.addEventListener('resize', () => {
      this.changeValue(this.coinValue)
    })
    this.changeValue(this.coinValue)
  },
  methods: {
    changeValue(value) {
      if(this.userWidth < 480 && value.length > 4) {
        const thousands = value.slice(0, 3)
        const tens = value.slice(3, -2)
        this.coinsValue = `${thousands},${tens}k`
      } else {
        this.coinsValue = value
      }
    }
  }
}
</script>