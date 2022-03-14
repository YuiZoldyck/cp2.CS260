<template>
<div id="app">
  <div id="menu">
    <div id="nav">
      <router-link to="/">
        <div class="menu-item home">
          <img src="/images/home.png">
          <p>Home</p>
        </div>
      </router-link>
      <router-link to="/about">
        <div class="menu-item about">
          <img src="/images/about.png">
          <p>About</p>
        </div>
      </router-link>
    </div>
    <div id="brand">
      <router-link to="/products">
        <img src="/images/finallogo.jpg">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/browse.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/cart9.png">
          <p>{{numberOfItems}}</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>


<script>
export default {
  computed: {
    numberOfItems() {
      return this.$root.$data.cart.length;
    }
  }
}
</script>


<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  width: 350px;
}

#nav {
  display: flex;
  justify-content: flex-start;

}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
  float: right;
  text-align: right;
}

.browse {
  margin-right: 50px;
}

.home {
  margin-right: 50px;
}

.home p{
  text-align: center;
}

.about p{
  text-align: center;
}
</style>
