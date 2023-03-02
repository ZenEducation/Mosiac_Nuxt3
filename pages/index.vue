<template>
  <div>
    <Sidebar
      :sidebarOpen="sidebarOpen"
      @close-sidebar="sidebarOpen.value = false"
    />
  </div>
</template>

<script setup>;
import Sidebar from "../partials/Sidebar.vue";
    const sidebarOpen = ref(false);
</script>



