<template>
  <div class="flex h-screen overflow-hidden">
    <NuxtLink to="/">Home Page</NuxtLink>
    <!-- Sidebar Wrapper -->
    <div
      id="sidebar-wrapper"
      class="w-64 lg:w-20 lg:sidebar-expanded:!w-64 2xl:!w-64"
    >
      <!-- Sidebar -->
      <Sidebar
        :sidebarOpen="sidebarOpen"
        @close-sidebar="sidebarOpen = false"
      />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import Sidebar from "../partials/Sidebar.vue";
import Header from "../partials/Header.vue";
// import { useRouter } from "vue-router";

export default {
  name: "Inbox",
  components: {
    Sidebar,
    Header,
  },
};
</script>


// The following code may work in Nuxt 3 but not in Nuxt 2
// const currentRoute = useRouter().currentRoute.value;
// console.log(currentRoute);
