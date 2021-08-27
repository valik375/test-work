<template>
  <div class="shop-card">
    <div class="shop-card__bonus" v-if="itemBonus">
      <div class="shop-card__bonus-body">
        <img class="shop-card__bonus-image" src="../../assets/images/card/bonusCoin.png" alt="small coin icon" >
        <span class="shop-card__bonus-text">x{{itemBonus}}</span>
      </div>
    </div>
    <img :src="require(`@/assets/images/card/${imagePath}`)" :alt="itemValue+itemName" class="shop-card__image">
    <div class="shop-card__content">
      <h3 class="shop-card__value">x{{itemValue}}</h3>
      <span class="shop-card__name">{{itemName}}</span>
    </div>
    <button class="shop-card__button">
      <span class="shop-card__button-text">Купить</span>
      <span class="shop-card__cost">
        <span v-if="itemCurrency === 'dollar'" class="shop-card__dollar">$</span>
        <span v-else class="shop-card__crystal">
          <img class="shop-card__crystal-icon" src="../../assets/images/card/buttonCrystalIcon.png" alt="">
        </span>
        {{itemPrice}}
      </span>
    </button>
  </div>
</template>

<script>
export default {
  props: ['imagePath', 'itemValue', 'itemName', 'itemPrice', 'itemCurrency', 'itemBonus'],
  name: "ShopCard"
}
</script>
