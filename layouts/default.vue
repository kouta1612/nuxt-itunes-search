<template>
  <div>
    <ToolBar/>
    <section class="container">
      <nuxt/>
    </section>
  </div>
</template>

<script>
import ToolBar from '~/components/ToolBar.vue';
export default {
  components: {
    ToolBar
  }
}
</script>

<style>
</style>

