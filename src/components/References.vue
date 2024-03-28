<script>
export default {
  name: 'References'
}
</script>

<template>
  <div class="container-fluid references">
    <div class="row title">
      <h2 class="h2-work">• Nos références •</h2>
    </div>
    <div class="row slider">
      <div class="bckgd"></div>
    </div>
  </div>
</template>

<style lang="scss">
.references {
  height: 600px;
  .title {
    text-align: center;
  }
  .slider {
    height: 100%;
    position: relative;
    .bckgd {
      position: absolute;
      background: url('../assets/images/DITO.png');
      height: 100%;
      opacity: 30%;
    }
  }
}
</style>