<template>
<div class="filters">
  <span
    v-for="filter in filters"
    :key="filter.value"
    @click="$emit('change-filter', filter.value)"
    class="filter"
    :class="{ active: selected === filter.value }"
    >{{ filter.label }}</span>
</div>
  
</template>

<script>
export default {
    name: "TodoFilter",
    props: ["selected"],
    setup() {
      const filters = [
        { lebal: "全部", value: "all" },
        { lebal: "已完成", value: "done" },
        { lebal: "未完成", value: "todo" },
      ];

      return { filters };
    },
};
</script>

<style>
.filters {
  display: flex;
  margin: 24px 2px;
  color: #C0C2CE; /* 默認淺灰色，未選中狀態 */
  font-size: 14px;
  cursor: pointer;
}

.filters .filter {
  margin-right: 14px;
  transition: 0.8s;
}

/* 選中狀態 */
.filters .filter.active {
  color: #6B729C;
  transform: scale(1.2);
}
</style>