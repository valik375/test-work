<template>
  <div class="donations">
    <img :src="require(`@/assets/images/navbar/${imagePath}`)" :alt="coinName" class="donations__image">
    <div class="donations__content">
      <span class="donations__value">{{coinValue}}</span>
      <span class="donations__coin-name">{{coinName}}</span>
    </div>
    <router-link :to="buyLink" class="donations__button">
      <svg class="donations__plus-icon" width="13" height="13" viewBox="0 0 13 13" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M8 0H5V5H0V8H5V13H8V8H13V5H8V0Z" fill="url(#paint0_linear)"/>
        <defs>
        <linearGradient id="paint0_linear" x1="6.5" y1="0" x2="6.5" y2="13" gradientUnits="userSpaceOnUse">
        <stop stop-color="#B1FFAF"/>
        <stop offset="1" stop-color="white"/>
        </linearGradient>
        </defs>
      </svg>
    </router-link>
  </div>
</template>

<script>

export default {
  props: ['imagePath', 'coinValue', 'coinName', 'buyLink']
}
</script>

<style>

</style>