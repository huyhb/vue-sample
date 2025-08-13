<template>
  <div class="dropdown-item" @click="handleClick">
    {{ item.text }}
  </div>
</template>

<script setup>
const props = defineProps({
  item: { type: Object, required: true },
  closeDropdown: { type: Function, required: true },
});

const emit = defineEmits(["select"]);

function handleClick() {
  props.closeDropdown();
  emit("select", props.item);
}
</script>

<style scoped>
.dropdown-item {
  padding: 8px 12px;
  cursor: pointer;
}
.dropdown-item:hover {
  background: #f0f0f0;
}
</style>
