<template>
  <header>
    <img class="logo" alt="Wheather Now logo" src="../assets/logo.svg">
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
};
</script>

<style scoped>
header {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 15px 0;
  background-color: #fff;
  box-shadow: 0 0 4px rgba(0,0,0,.15);
}

header .logo {
  min-width: 200px;
}
</style>
