<script setup lang="ts">
import { ref } from "vue";
import { useMainStore } from "@/store/index";
import { NButton } from "naive-ui";

defineProps<{ msg: string }>();
const mainStore = useMainStore();
const handleChangeName = () => {
  mainStore.insertPost("修改名称");
};

const count = ref(0);
</script>

<template>
  <h3>{{ mainStore.name }} {{ mainStore.nameLength }}</h3>
  <h1>{{ msg }}</h1>

  <div class="card">
    <n-button @click="handleChangeName">change name</n-button>
    <button type="button" @click="count++">counts is {{ count }}</button>
    <p>
      Edit
      <code>login/LoginPage.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style lang="scss" scoped>
.read-the-docs {
  color: $red-color;
}
</style>
