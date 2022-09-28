<template>
  <pv-toast/>
  <header>
    <pv-toolbar class="bg-primary">
      <template #start>
        <pv-button icon="pi pi-bars"
                   class="p-button-text text-white"
                   @click="drawer = !drawer"></pv-button>
        <h3>My Property</h3>
      </template>
      <template #end>
        <div class="flex-column">
          <router-link v-for="item in items"
                       :to="item.to"
                       custom
                       v-slot="{navigate, href}"
                       :key="item.label">
            <pv-button
              class="p-button-text text-white"
              :href="href"
              @click="navigate">{{ item.label }}</pv-button>
          </router-link>
        </div>
      </template>
    </pv-toolbar>
  </header>
  <pv-sidebar v-model:visible="drawer"></pv-sidebar>
  <router-view></router-view>
</template>
<script>
  export default {
    data() {
      return {
        drawer: false,
        items: [
          { label: 'Home', to: '/home' },
         // { label: 'About', to: '/about' },
          { label: 'Property', to: '/tutorials' },
        ]
      }
    }
  }
</script>
