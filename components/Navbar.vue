<template>
  <div class="text-main flex align-center hide-scrollbar overflow-x-auto">
    <div
      v-for="(tab, index) in tabs"
      :id="tab"
      :key="index"
      class="border-2 bg-white py-2 px-8"
      :class="{
        'mr-5 rounded-r-2xl': index == tabs.length - 1,
        'ml-5 rounded-l-2xl': index == 0,
        'bg-selected text-white': tab == selectedTab,
      }"
      @click="selectTab(tab)"
    >
      {{ tab }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: ['Arbeitnehmer', 'Arbeitgeber', 'Temporärbüro'],
      selectedTab: 'Arbeitnehmer',
    }
  },
  methods: {
    selectTab(tab) {
      this.selectedTab = tab
      document.getElementById(tab).scrollIntoView({
        inline: 'center',
        behavior: 'smooth',
      })
    },
  },
}
</script>

<style scoped>
.bg-selected {
  background-color: #81e6d9;
}
</style>
