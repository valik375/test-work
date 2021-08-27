<template>
  <TheNavbar
      :navbarData="walletValue"
  />
  <section class="shop">
    <div class="shop__background background">
      <img src="./assets/images/leftMonster.png" alt="" class="background__left-image">
      <img src="./assets/images/mainBg.png" alt="" class="background__main-image">
      <img src="./assets/images/rightMonster.png" alt="" class="background__right-image">
      <img src="./assets/images/rightMonsterMobile.png" alt="" class="background__mobile-image">
      <div ref="backgroundShadow" class="background__bottom-shadow background__bottom-shadow_active"></div>
    </div>
    <div class="wrapper">
      <ShopNavigation
          @getClick="getClickFromNavigation"
      />
      <div class="shop__container" ref="shopContainer">
        <div class="shop__wrapper" v-if="tabIsActive === 'bank'">
          <h1 class="shop__title">Кристаллы Незера</h1>
          <div class="shop__items-container">
            <ShopCard
                v-for="(item, index) in bankCrystals"
                :key="index"
                :imagePath="item.imagePath"
                :itemValue="item.value"
                :itemName="item.name"
                :itemPrice="item.itemPrice"
                :itemCurrency="item.currency"
                :itemBonus="item.bonus"
            />
          </div>
          <hr class="shop__line">
          <h1 class="shop__title">Монеты Незера</h1>
          <div class="shop__items-container">
            <ShopCard
                v-for="(item, index) in bankCoins"
                :key="index"
                :imagePath="item.imagePath"
                :itemValue="item.value"
                :itemName="item.name"
                :itemPrice="item.itemPrice"
            />
          </div>
        </div>
        <div class="shop__empty" v-else>
          <h1 class="shop__empty-message">Простите, пока что сдесь ничего нет.</h1>
        </div>
      </div>

    </div>
  </section>
</template>

<script>
import TheNavbar from './components/Navbar/TheNavbar.vue'
import ShopNavigation from "./components/ShopNavigation/ShopNavigation";
import ShopCard from "./components/ShopCard/ShopCard";

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
    ],
    tabIsActive: 'bank',
    bankCrystals: [
      {
        imagePath: 'crystalsIcon-1.png',
        value: '100',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-2.png',
        value: '500',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-3.png',
        value: '1000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-4.png',
        value: '1500',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-5.png',
        value: '100',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-6.png',
        value: '500',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-7.png',
        value: '1000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-8.png',
        value: '1500',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      },
      {
        imagePath: 'crystalsIcon-9.png',
        value: '100',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'dollar',
        bonus: '500'
      }
    ],
    bankCoins: [
      {
        imagePath: 'coinsIcon-1.png',
        value: '1000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
      {
        imagePath: 'coinsIcon-2.png',
        value: '5000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
      {
        imagePath: 'coinsIcon-3.png',
        value: '10000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
      {
        imagePath: 'coinsIcon-4.png',
        value: '10000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
      {
        imagePath: 'coinsIcon-5.png',
        value: '1000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
      {
        imagePath: 'coinsIcon-6.png',
        value: '5000',
        name: 'Handful of Coins',
        itemPrice: '10',
        currency: 'crystals'
      },
    ]
  }),
  mounted() {
    document.addEventListener('scroll', () => {
      const shopContainer = this.$refs.shopContainer
      const windowOffsetTop = window.scrollY
      const backgroundShadow = this.$refs.backgroundShadow
      if(windowOffsetTop !== 0) {
        shopContainer.classList.add('shop__container_active')
        backgroundShadow.classList.add('background__bottom-shadow_active')
      } else {
        shopContainer.classList.remove('shop__container_active')
        backgroundShadow.classList.remove('background__bottom-shadow_active')
      }
    })
  },
  methods: {
    getClickFromNavigation(data) {
      this.tabIsActive = data
    }
  },
  components: {
    TheNavbar, ShopNavigation, ShopCard
  }
}
</script>
