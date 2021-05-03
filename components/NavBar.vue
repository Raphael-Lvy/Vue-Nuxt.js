<template>
    <div class='nav'>
        <nuxt-link to="/" class="brand">To Do list</nuxt-link>
        <nav>
            <nuxt-link to="/" >To Do</nuxt-link>&nbsp;|
            <nuxt-link to="/about">A propos</nuxt-link>
        </nav>    
        
    </div>
</template>

<style scoped>
.brand {
  font-family: "Montserrat", sans-serif;
  font-weight: 700;
  font-size: 1.5em;
  color: #39b982;
  text-decoration: none;
}
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 60px;
}
.nav .nav-item {
    box-sizing: border-box;
    margin: 0 5px;
    color: rgba(0, 0, 0, 0.5);
    text-decoration: none;
}
.nav .nav-item.router-link-exact-active {
      color: #39b982;
      border-bottom: solid 2px #39b982;
    }
    .nav a {
      display: inline-block;
      transition: 0.1s;
    }

    .nav a:hover {
        color: #32da91;
    }
</style>