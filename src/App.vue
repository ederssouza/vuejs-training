<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
@import './assets/css/bootstrap.min.css';

#app {
  background-color: #fff;
  padding: 100px 0 50px;
}

.h1, .h2, .h3, .h4, .h5, .h6,
h1, h2, h3, h4, h5, h6 {
  margin-bottom: 1.5rem;
}

a:not(.navbar-brand),
a:not(.navbar-brand):hover {
  color: #3fba84;
}

body {
  color: #30485e;
}

.h1, h1 {
  font-size: 26px;
}

.btn-success {
  color: #fff;
  background-color: #3fba84 !important;
  border-color: #3fba84 !important;
}

.btn-primary {
  color: #fff;
  background-color: #30485e !important;
  border-color: #30485e !important;
}

.bg-success {
  background-color: #3fba84 !important;
}

.small {
  font-size: 60%;
}
</style>
