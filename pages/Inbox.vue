<template>
  <div class="flex h-screen overflow-hidden">
    <!-- Sidebar Wrapper -->
    <div id="sidebar-wrapper" class="w-64 lg:w-20 lg:sidebar-expanded:!w-64 2xl:!w-64">
      <!-- Sidebar -->
      <Sidebar :sidebarOpen="sidebarOpen" @close-sidebar="sidebarOpen = false" />
    </div>

    <!-- Content area -->
    <div class="relative flex flex-col flex-1 overflow-y-auto overflow-x-hidden">
      <!-- Site header -->
      <Header :sidebarOpen="sidebarOpen" @toggle-sidebar="sidebarOpen = !sidebarOpen" class="z-40"/>

      <main>
        <div class="relative flex">
          <!-- Inbox sidebar -->
          <InboxSidebar :inboxSidebarOpen="inboxSidebarOpen" @close-inboxsidebar="inboxSidebarOpen = false" />

          <!-- Inbox body -->
          <InboxBody :inboxSidebarOpen="inboxSidebarOpen" @toggle-inboxsidebar="inboxSidebarOpen = !inboxSidebarOpen" />
        </div>
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Sidebar from "../partials/Sidebar.vue";
import Header from "../partials/Header.vue";
import InboxSidebar from "../partials/inbox/InboxSidebar.vue";
import InboxBody from "../partials/inbox/InboxBody.vue";

// export default {

// setup() {
const sidebarOpen = ref(false)
const inboxSidebarOpen = ref(false)

    // return {
    //   sidebarOpen,
    //   inboxSidebarOpen,
    // };
  // },
// };
</script>