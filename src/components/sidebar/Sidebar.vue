<script>
import SidebarLink from './SidebarLink'
import { collapsed, toggleSidebar, sidebarWidth } from './state'

export default {
  props: {},
  components: { SidebarLink },
  setup() {
    return { collapsed, toggleSidebar, sidebarWidth }
  }
}
</script>

<template>
  <div class="sidebar" :style="{ width: sidebarWidth }">
    <h1>
      <span v-if="collapsed">
        <br>
        <br>
        <br>
        <br>


      </span>
    </h1>

    <SidebarLink to="/">📅 Connect</SidebarLink>
    <SidebarLink to="/events">💁 Events</SidebarLink>
    <SidebarLink to="/chat">💬 Chat</SidebarLink>
    <SidebarLink to="/profil">👤 Profil </SidebarLink>

    <span
      class="collapse-icon"
      :class="{ 'rotate-180': collapsed }"
      @click="toggleSidebar"
    >
      <i class="fas fa-angle-double-left" />
    </span>
  </div>
</template>

<style>
:root {
  --sidebar-bg-color: #000000;
  --sidebar-item-hover: #ff0000;
  --sidebar-item-active: #ff0000;
}
</style>

<style scoped>
.sidebar {
  color: rgb(0, 0, 0);
  background-color: var(--sidebar-bg-color);

  float: left;
  position: fixed;
  z-index: 1;
  top: 17%;
  left: 0;
  bottom: 10px;
  padding: 0.1em;

  transition: 0.3s ease;

  display: flex;
  flex-direction: column;
}

.sidebar h1 {
  height: 2.5em;
}

.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;

  color: rgba(255, 255, 255, 0.7);

  transition: 0.2s linear;
}

.rotate-180 {
  transform: rotate(180deg);
  transition: 0.2s linear;
}
</style>
