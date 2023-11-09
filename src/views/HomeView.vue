<script setup lang="ts">
import {ref} from 'vue';
import {useRouter} from 'vue-router';

const selectedIndex = ref(1)
const testShow = ref(true)
const router = useRouter()
const clickIndex = (index: number): void => {
  selectedIndex.value = index
  testShow.value = false
  setTimeout(() => {
    testShow.value = true
  }, 10)
}
</script>

<template>
  <main>
    <div class="row">
      <div
          v-for="(item,idx) in 16"
          :key="idx"
      >
        <div style="width: 100px; height: 100px; background: #9C27B0; text-align: center; margin: 5px"
             @click="clickIndex(item)"
        >
          {{ item }}
        </div>
      </div>
    </div>
  </main>
</template>
<style>
.row {
  display: grid;
  grid-template-columns: repeat(4, 100px);
  gap: 40px;
  padding: 0 60px;
}
</style>
