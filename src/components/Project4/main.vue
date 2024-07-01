<script setup>
  import { ref } from 'vue';

  const items = ref([
    {
      title: "Banu Putih",
      content: "lkmasdk knaskdn kjnasdn iqwdnq jq jqkas kasodq oknasdnkqw kjansdonq jnasdlas ojnqownd knaskndas oknasdm kjasnd",
      open: false
    },
    {
      title: "Banu Putih",
      content: "lkmasdk knaskdn kjnasdn iqwdnq jq jqkas kasodq oknasdnkqw kjansdonq jnasdlas ojnqownd knaskndas oknasdm kjasnd",
      open: false
    },
    {
      title: "Banu Putih",
      content: "lkmasdk knaskdn kjnasdn iqwdnq jq jqkas kasodq oknasdnkqw kjansdonq jnasdlas ojnqownd knaskndas oknasdm kjasnd",
      open: false
    }
  ])

  const toggleAccordion = (idx) => {
    items.value = items.value.map((item, i) => ({
      ...item,
      open: i === idx ? !item.open : false
    }))
  }

</script>

<template>
  <div class="accordion-container">
    <div v-for="(item, i) in items" :key="i" class="accordion">
      <div class="accordion-header" @click="toggleAccordion(i)">
        {{ item.title }}
        <span class="arrow-icon">{{ item.open ? "▼" : "▶"}}</span>
      </div>

      <div class="accordion-content" v-show="item.open">{{ item.content }}</div>
    </div>
  </div>
</template>

<style scoped>
  .accordion-container {
  max-width: 800px;
  margin: 50px auto;
}

.accordion {
  border: 1px solid #ddd;
  border-radius: 4px;
  overflow: hidden;
  margin-bottom: 10px;
}

.accordion-header {
  background-color: #3498db;
  color: #fff;
  padding: 15px;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.arrow-icon {
  font-size: 20px;
}

.accordion-content {
  padding: 15px;
  display: none;
  border-top: 1px solid #ddd;
  background-color: #f9f9f9;
  color: #333;
}

.accordion-content[style] {
  display: block;
}
</style>