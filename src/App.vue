<template>
  <header>
  <div id="nav">
    <router-link to="/">{{ $t("home") }}</router-link> |
    <router-link to="/about">{{ $t("about") }}</router-link>
    <LocaleSwitcher />
  </div>
  </header>
  <router-view/>
</template>

<script>
import LocaleSwitcher from '@/components/LocaleSwitcher'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
export default {
  components: { LocaleSwitcher }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding-top: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
