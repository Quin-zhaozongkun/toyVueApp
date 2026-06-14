<script setup lang="ts">
import { computed, ref } from 'vue'

interface Props {
  msg: string
}

defineProps<Props>()

const count = ref<number>(0)

const countLabel = computed<string>(() => `当前计数：${count.value}`)

const increment = (): void => {
  count.value += 1
}
</script>

<template>
  <div class="hello-world">
    <p class="hello-world__eyebrow">Vue 3 Composition API</p>
    <h1>{{ msg }}</h1>

    <div class="hello-world__card">
      <button type="button" @click="increment">{{ countLabel }}</button>
      <p>
        当前组件已改为
        <code>&lt;script setup lang=&quot;ts&quot;&gt;</code>
        和
        <code>&lt;style scoped lang=&quot;scss&quot;&gt;</code>
        格式。
      </p>
    </div>
  </div>
</template>

<style scoped lang="scss">
.hello-world {
  display: grid;
  gap: 1.5rem;
  justify-items: center;

  &__eyebrow {
    margin: 0;
    color: #42b883;
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  h1 {
    max-width: 12ch;
    margin: 0;
    font-size: clamp(2.4rem, 8vw, 4.5rem);
    line-height: 1;
  }

  &__card {
    display: grid;
    gap: 1rem;
    justify-items: center;
    max-width: 36rem;
    padding: 2rem;
    border-radius: 1.5rem;
    background: rgba(100, 108, 255, 0.08);

    p {
      margin: 0;
      color: #c9d1d9;
    }
  }
}
</style>
