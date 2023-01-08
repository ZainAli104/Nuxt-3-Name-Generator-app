<template>
  <div class="card">
    <h4>{{ name }}</h4>
    <p @click="removeName">x</p>
  </div>
</template>

<script setup lang="ts">
import { e } from 'unimport/dist/types-488f6d65';

interface NameProps {
    name: string,
    index: number
}

const props = defineProps<NameProps>();

const emit = defineEmits(["remove"])

const removeName = () => {
    emit("remove", props.index)
}
</script>

<style scoped>
.card {
  background-color: rgb(27, 60, 138);
  width: 28%;
  color: white;
  padding: 0.1rem;
  margin-right: 0.5rem;
  border-radius: 1rem;
  margin-bottom: 1rem;
  position: relative;
}
.card p {
  position: absolute;
  top: -20%;
  left: 92.5%;
  cursor: pointer;
  color: rgb(255, 255, 255, 0.178);
}
</style>