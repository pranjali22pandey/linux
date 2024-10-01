<template>
  <ifx-navbar show-logo="true" application-name="Application name" fixed="true">
    <ifx-navbar-item slot="left-item" hide-label="false">
      <RouterLink to="/" class="nav-link">Home</RouterLink>
    </ifx-navbar-item>
    <ifx-navbar-item slot="left-item" hide-label="false">
      <RouterLink to="/ag-grid" class="nav-link">AG-Grid</RouterLink>
    </ifx-navbar-item>
    <ifx-search-bar slot="search-bar-right" v-model="searchQuery" is-open="false" show-close-button="true"></ifx-search-bar>
    <ifx-navbar-item slot="right-item" class="dds-layout-nav-bar-icons" hide-label="false">
      <ifx-icon icon="image-24"></ifx-icon>
    </ifx-navbar-item>
    <ifx-navbar-item slot="right-item" hide-label="false">
      <ifx-icon icon="image-24"></ifx-icon>
    </ifx-navbar-item>
    <ifx-navbar-item slot="right-item" hide-label="false">
    </ifx-navbar-item>
  </ifx-navbar>
  <router-view :userName="userName" />
</template>

<script setup>
import { ref } from "vue";

const searchQuery = ref(""); 

</script>

<style>
.dds-layout-nav-bar-icons {
  margin: 2px 5px;
  padding: 3px;
  cursor: pointer;
}
.nav-link {
  text-decoration: none;
  color: inherit; 
}

</style>
