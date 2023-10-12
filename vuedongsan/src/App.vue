<template>
<div>
  <div class="menu">
    <a v-for="(a, i) in 웅냐" :key="i"> {{ a }}</a>
  </div>

  <div v-for="(a,i) in products" :key="i">
    <h4>{{products[i]}}</h4>
    <p>50만원</p>
  </div>

</div>

  </template>

<script>

export default {
  name: 'App',
  data() {
    return {
      name1: '행복',
      price1: 60,
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],

      웅냐: ['home', 'solution', 'about'],
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
