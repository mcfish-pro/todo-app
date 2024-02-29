<template>
<div class="filters">
        <span class="filter active">全部</span>
        <span class="filter">已完成</span>
        <span class="filter">未完成</span>
      </div>
  
</template>

<script>
export default {
    name: "TodoFilter",

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