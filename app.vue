<template>
  <div id="main-template" class="text-body bg-dark">
    <navigation/>
    <div>
      <nuxt-page/>
    </div>
  </div>
</template>
<script setup lang="ts">
import Navigation from "~/components/layouts/navigation.vue";
</script>
<style lang="scss" scoped>
#main-template {
  min-height: 100vh;
}
</style>