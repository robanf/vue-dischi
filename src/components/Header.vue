<template>
  <div>
      <div class="my-container">
            <img class="logo" src="@/img/logo.png" alt="">
        </div>

      
  </div>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style lang="scss">
    .my-container{
        height: 100px;
        background-color: #2e3a46;
        display: flex;
        .logo{
            height: 85px;
            width: auto;
        }

    }
</style>