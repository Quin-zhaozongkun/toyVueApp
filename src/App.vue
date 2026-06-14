<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'

interface FeatureItem {
  title: string
  description: string
}

const features: FeatureItem[] = [
  {
    title: 'TypeScript',
    description: '使用类型定义提升组件数据和属性的可维护性。',
  },
  {
    title: 'Vue 3',
    description: '通过 <script setup> 组合式 API 编写更简洁的组件逻辑。',
  },
  {
    title: 'Scss',
    description: '使用嵌套样式和变量组织页面表现层代码。',
  },
]
</script>

<template>
  <main class="app-shell">
    <section class="hero">
      <div class="hero__logos" aria-label="技术栈 logo">
        <a href="https://vite.dev" target="_blank" rel="noreferrer">
          <img src="/vite.svg" class="hero__logo" alt="Vite logo" />
        </a>
        <a href="https://vuejs.org/" target="_blank" rel="noreferrer">
          <img src="./assets/vue.svg" class="hero__logo hero__logo--vue" alt="Vue logo" />
        </a>
      </div>

      <HelloWorld msg="Vite + Vue 3 + TypeScript + Scss" />
    </section>

    <section class="features" aria-label="代码格式说明">
      <article v-for="feature in features" :key="feature.title" class="features__item">
        <h2>{{ feature.title }}</h2>
        <p>{{ feature.description }}</p>
      </article>
    </section>
  </main>
</template>

<style scoped lang="scss">
.app-shell {
  width: min(100%, 960px);
  margin: 0 auto;
  padding: 4rem 1.5rem;
}

.hero {
  display: grid;
  gap: 2rem;
  justify-items: center;
  text-align: center;

  &__logos {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
  }

  &__logo {
    height: 6rem;
    padding: 1rem;
    will-change: filter;
    transition: filter 300ms, transform 300ms;

    &:hover {
      filter: drop-shadow(0 0 2rem rgba(100, 108, 255, 0.67));
      transform: translateY(-0.25rem);
    }

    &--vue:hover {
      filter: drop-shadow(0 0 2rem rgba(66, 184, 131, 0.67));
    }
  }
}

.features {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 1rem;
  margin-top: 3rem;

  &__item {
    padding: 1.25rem;
    border: 1px solid rgba(100, 108, 255, 0.2);
    border-radius: 1rem;
    background: rgba(255, 255, 255, 0.04);
    text-align: left;

    h2 {
      margin: 0 0 0.5rem;
      color: #42b883;
      font-size: 1.1rem;
    }

    p {
      margin: 0;
      color: #c9d1d9;
    }
  }
}

@media (max-width: 720px) {
  .app-shell {
    padding-block: 2rem;
  }

  .features {
    grid-template-columns: 1fr;
  }
}
</style>
