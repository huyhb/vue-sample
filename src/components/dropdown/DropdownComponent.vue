<template>
  <div ref="dropdownRef" :id="id" class="dropdown">
    <button @click="isOpen = !isOpen" :class="{ isActive: isOpen }">
      <slot />
    </button>
    <div class="dropdown-list" v-if="isOpen">
      <Item v-for="(item, index) in arrays" :key="index" :item="item" :closeDropdown="callToClose">
        {{ item.text }}
      </Item>
    </div>
  </div>
</template>


<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
import Item from "./Item.vue"; // đường dẫn tới component Item


// Props
defineProps({
  arrays: {
    type: Array,
    default: () => [],
  },
  id: {
    type: String,
    required: true,
  },
});

// State
const dropdownRef = ref(null); // <-- thêm dòng này
const isOpen = ref(false);

// Methods
function callToClose() {
  isOpen.value = false;
}

// Hàm kiểm tra click ngoài
const handleClickOutside = (event) => {
  if (dropdownRef.value && !dropdownRef.value.contains(event.target)) {
    isOpen.value = false;
  }
};

onMounted(() => {
  document.addEventListener('click', handleClickOutside);
});

onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside);
});

</script>

<style scoped>
.dropdown {
  position: relative;
  display: inline-block;
}

button {
  padding: 8px 12px;
  border: 1px solid #ccc;
  background: white;
  cursor: pointer;
}

button.isActive {
  border-color: #007bff;
  background: #f0f8ff;
}

.dropdown-list {
  position: absolute;
  top: 100%;
  left: 0;
  width: 180px;
  border: 1px solid #ccc;
  background: white;
  z-index: 100;
}
</style>
