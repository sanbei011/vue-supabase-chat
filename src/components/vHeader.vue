<script setup>
import userIcon from '@/components/user-icon.vue'
import useStore from '@/store.js'
import getRandomName from '@/utils/getRandomName'

const store = useStore()
</script>
<template>
  <header
    class="w-full p-3 bg-black-100 flex justify-center z-10 select-none border-neutral-700 border-b"
    id="header"
  >
    <div class="flex items-center justify-between w-full">
      <h1 class="font-medium animate-charcter">莘莘酒语交流平台</h1>

      <div class="flex items-center gap-3">
        <span
          class="text-base font-medium cursor-pointer whitespace-pre"
          id="name"
          @click="store.setName(getRandomName())"
          >{{ store.getName() }}</span
        >
        <user-icon class="w-5 h-5" />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  div {
    max-width: var(--content-width);
  }
}

.animate-charcter {
  text-transform: uppercase;
  background-image: linear-gradient(-225deg, #32963a 0%, #3fa321 29%, #1ad896 67%, #80ff00 100%);
  background-size: auto auto;
  background-clip: border-box;
  background-size: 200% auto;
  background-clip: text;
  text-fill-color: transparent;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: text_clip 3s linear infinite;
  display: inline-block;
}

@keyframes text_clip {
  to {
    background-position: 200% center;
  }
}
</style>
