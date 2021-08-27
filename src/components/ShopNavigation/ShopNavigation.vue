<template>
  <div class="shop-navigation">
    <button
        class="shop-navigation__link"
        :class="index === buttonIndex ? 'active' : ''"
        v-for="(item, index) in navLinks"
        :key="index"
        @click="clickOnShopButton(item.data, index)"
    >
      <span class="shop-navigation__text">{{item.text}}</span>
      <span class="shop-navigation__border"></span>
    </button>
  </div>
</template>

<script>
export default {
  name: "ShopNavigation.vue",
  data: () => ({
    navLinks: [
      {
        text: 'Монстр Боксы',
        data: 'monsterBox'
      },
      {
        text: 'Банк',
        data: 'bank'
      },
      {
        text: 'Наборы',
        data: 'kits'
      },
      {
        text: 'Спецпредложения',
        data: 'specials'
      },
      {
        text: 'Промокоды',
        data: 'promoCodes'
      }
    ],
    buttonIndex: 1
  }),
  methods: {
    clickOnShopButton(data, index) {
      this.buttonIndex = index
      this.$emit('getClick', data)
    }
  }
}
</script>
