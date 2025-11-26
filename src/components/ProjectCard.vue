<template>
  <component 
    :is="link ? 'a' : 'div'" 
    :href="link || undefined" 
    :target="link ? '_blank' : undefined"
    class="bg-gray-900 rounded-2xl overflow-hidden border border-gray-800 hover:border-green-500 transition-all duration-300"
    :class="link ? 'cursor-pointer hover:transform hover:scale-105' : ''">
    <div class="h-48 bg-linear-to-br" :class="gradient"></div>
    <div class="p-6">
      <h3 class="text-xl font-bold mb-2">{{ name }}</h3>
      <p class="text-gray-400 mb-4">{{ description }}</p>
      <div class="flex flex-wrap gap-2">
        <span v-for="tech in technologies" :key="tech"
          class="px-3 py-1 bg-gray-800 rounded-full text-sm text-gray-300">
          {{ tech }}
        </span>
      </div>
    </div>
  </component>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  technologies: {
    type: Array,
    required: true
  },
  gradient: {
    type: String,
    required: true
  },
  link: {
    type: String,
    default: ''
  }
})
</script>
