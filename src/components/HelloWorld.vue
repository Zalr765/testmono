<template>
  <div class="counter">
    <img src="../assets/bronze-coin-swiss-franc-icon.svg" alt="">
    {{counter}}
  </div>
  <div class="coin" @click='CoinPlus' :class="{ 'scale': isClicked }"></div>
</template>

<script>

export default {
  data()
  {
    let counter;
    document.cookie.match(/counter=(.+?)(;|$)/) ? counter = Number(document.cookie.match(/counter=(.+?)(;|$)/)[1]) : counter = 0
    return{
      counter,
      clickPower: 1,
      isClicked:false,
      tg : null
    }
  },
  methods:
  {
    CoinPlus()
    {
      this.counter+=this.clickPower;
      this.isClicked = true;
      setTimeout(()=> this.isClicked = false, 40)
      document.cookie = `counter = ${this.counter}`
      alert(this.tg)
    },
  },
  mounted(){
    this.tg = window.Telegram.WebApp.initDataUnsafe?.user?.id
  }
}
</script>

<style scoped>
.counter
{
  display: flex;
  align-items: center;
  color: white;
  font-size: calc((1vw + 1vh) * 1.8);
  font-family: Arial;
  position: absolute;
  top: calc((1vw + 1vh) * 2);
  left: calc((1vw + 1vh) * 3);
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  -o-user-select: none;
  user-select: none;
}
.counter img
{
  margin-right: calc((1vw + 1vh)*1.3);
  width: calc((1vw + 1vh) * 2);
}
.coin
{
  width: calc((1vw + 1vh) * 17);
  height: calc((1vw + 1vh) * 17);
  background-image: url('../assets/bronze-coin-swiss-franc-icon.svg');
  background-size: contain;
  transition: .03s;
  position: relative;
  background-repeat: no-repeat;
}
.scale
{
  transform: scale(.93);
}
</style>
