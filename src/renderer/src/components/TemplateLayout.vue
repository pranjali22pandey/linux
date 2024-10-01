<template>
  <div class="dds-layout-with-header-layout">
    <NavBar />
    <div class="dds-layout-with-header-layout-content">
    </div>
  </div>
 
</template>

<script>
import NavBar from "./NavBar.vue";

export default {
  name: 'TemplateLayout',
  components: {
    NavBar,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.dds-layout-with-header-layout {
  display: flex;
  flex-direction: column;

  .dds-layout-with-header-layout-content {
    width: 100%;
  }
}
</style>
