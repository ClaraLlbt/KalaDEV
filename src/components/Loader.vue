<template lang="">
    <div class="loader">
        <img class="rotate-center" src="../assets/kaladev-logo.svg" width="200" height="200" alt=""> 
    </div>
</template>
<script>
export default {
    name: "Loader"
    
}
</script>
<style lang="scss">
.loader{
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    top: 35%;
    bottom: 0;
    text-align: center;
}
.rotate-center {
	animation: rotate-center 1.5s 1s ease-in-out infinite forwards;
    transform: scale(1.5);
}

@keyframes rotate-center {
0%{
    transform: rotate(0) scale(1.5);
    opacity: 1;

  }

100% {
    transform: rotate(360deg) scale(1.5);
    opacity: 0;
    transition: opacity 0.5s forwards;
  }
}
</style>