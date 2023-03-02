<template>
  <div class="flex h-screen overflow-hidden">
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

    <!-- Content area -->
    <div
      class="
        relative
        flex flex-col flex-1
        overflow-y-auto overflow-x-hidden
        bg-white
      "
    >
      <!-- Site header -->
      <Header
        :sidebarOpen="sidebarOpen"
        @toggle-sidebar="sidebarOpen = !sidebarOpen"
      />

      <main>
        <div class="relative grid grid-cols-12">
          <!-- Profile sidebar -->
          <div class="col-span-3">
            <ProfileSidebar
              id="ProfileSidebar"
              :profileSidebarOpen="profileSidebarOpen"
              @close-profilesidebar="profileSidebarOpen = false"
            />
          </div>
          <div class="col-span-9">
            <!-- Profile body -->
            <ProfileBody
              :profileSidebarOpen="profileSidebarOpen"
              @toggle-profilesidebar="profileSidebarOpen = !profileSidebarOpen"
            />
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import Sidebar from "../../partials/Sidebar.vue";
import Header from "../../partials/Header.vue";
import ProfileSidebar from "../../partials/community/ProfileSidebar.vue";
import ProfileBody from "../../partials/community/ProfileBody.vue";

export default {
  name: "Profile",
  components: {
    Sidebar,
    Header,
    ProfileSidebar,
    ProfileBody,
  },
  setup() {
    const sidebarOpen = ref(false);
    const profileSidebarOpen = ref(false);

    return {
      sidebarOpen,
      profileSidebarOpen,
    };
  },
};
</script>