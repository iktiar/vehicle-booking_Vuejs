<template>
  <div class="container">
    <app-header></app-header>
    <div class="row">
        <div class="col-xs-12">
            <router-view></router-view>
        </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header'

export default {
    components: {
        appHeader: Header
    },
    created () {
        const token = localStorage.getItem('token')

        if (token) {
            this.$store.dispatch('setToken', token)
        }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
