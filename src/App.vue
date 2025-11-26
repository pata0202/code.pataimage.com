<template>
  <div class="min-h-screen bg-black text-white">
    <!-- Hero Section -->
    <header class="container mx-auto px-6 py-20">
      <div class="text-center">
        <p class="text-xl md:text-2xl text-gray-400 mb-2">Hi, I'm</p>
        <h1
          class="text-6xl md:text-8xl font-bold mb-6 bg-linear-to-r from-purple-400 via-pink-500 to-red-500 bg-clip-text text-transparent">
          Pata
        </h1>
        <p class="text-xl md:text-2xl text-gray-400 mb-8">
          善於程式設計與規劃，打造穩固且優秀的應用程式
        </p>
        <div class="flex justify-center gap-4">
          <a href="#skills"
            class="px-6 py-3 bg-linear-to-r from-purple-500 to-pink-500 rounded-full font-semibold hover:opacity-80 transition">
            查看技能
          </a>
          <a href="#projects"
            class="px-6 py-3 border border-gray-600 rounded-full font-semibold hover:bg-gray-800 transition">
            專案作品
          </a>
        </div>
      </div>
    </header>

    <!-- Skills Section -->
    <section id="skills" class="container mx-auto px-6 py-20">
      <h2
        class="text-4xl md:text-5xl font-bold text-center mb-16 bg-linear-to-r from-cyan-400 via-blue-500 to-purple-500 bg-clip-text text-transparent">
        技術能力
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Skill Card -->
        <div v-for="skill in skills" :key="skill.name"
          class="bg-gray-900 rounded-2xl p-6 border border-gray-800 hover:border-purple-500 transition-all duration-300 hover:transform hover:scale-105">
          <div class="text-4xl mb-4">{{ skill.icon }}</div>
          <h3 class="text-xl font-bold mb-2">{{ skill.name }}</h3>
          <p class="text-gray-400">{{ skill.description }}</p>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="container mx-auto px-6 py-20">
      <h2
        class="text-4xl md:text-5xl font-bold text-center mb-16 bg-linear-to-r from-green-400 via-emerald-500 to-teal-500 bg-clip-text text-transparent">
        專案作品
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <ProjectCard v-for="project in projects" :key="project.name" :name="project.name"
          :description="project.description" :technologies="project.technologies" :gradient="project.gradient"
          :link="project.link" />
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="container mx-auto px-6 py-20">
      <h2
        class="text-4xl md:text-5xl font-bold text-center mb-8 bg-linear-to-r from-rose-400 via-fuchsia-500 to-indigo-500 bg-clip-text text-transparent">
        聯絡我
      </h2>
      <p class="text-center text-gray-400 mb-8 text-lg">
        有任何合作機會或問題，歡迎與我聯繫！
      </p>
      <div class="flex justify-center gap-6">
        <a href="https://github.com/pata0202" target="_blank"
          class="w-12 h-12 flex items-center justify-center rounded-full bg-gray-800 hover:bg-gray-700 transition">
          <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
          </svg>
        </a>
        <a href="mailto:pata@pataimage.com"
          class="w-12 h-12 flex items-center justify-center rounded-full bg-gray-800 hover:bg-gray-700 transition">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
          </svg>
        </a>
        <a href="https://www.linkedin.com/in/pey-chern-shieh-b590b2147" target="_blank"
          class="w-12 h-12 flex items-center justify-center rounded-full bg-gray-800 hover:bg-gray-700 transition">
          <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" />
          </svg>
        </a>
      </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-gray-800 py-8">
      <p class="text-center text-gray-500">
        © 2025 Pata
      </p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ProjectCard from './components/ProjectCard.vue'

const skills = ref([
  {
    name: 'C# Web API',
    icon: '🔷',
    description: 'ASP.NET Core Web API 開發、RESTful 設計、Entity Framework'
  },
  {
    name: 'Vue.js',
    icon: '💚',
    description: 'Vue 3 Composition API、Pinia 狀態管理、Vite 建置工具'
  },
  {
    name: 'MSSQL',
    icon: '🗄️',
    description: 'SQL Server 資料庫設計、T-SQL 查詢、預存程序'
  },
  {
    name: 'Docker',
    icon: '🐳',
    description: '容器化部署、Docker Compose、映像檔管理'
  }
])

const projects = ref([
  {
    name: '食在營養',
    description: '為營養師團隊打造的線上平台，包涵團隊介紹與文章分享的前後台功能',
    technologies: ['C#', 'PostgreSQL'],
    gradient: 'from-orange-600 to-yellow-600',
    link: ''
  },
  {
    name: '空中電波-內部管理平台',
    description: '全套前後端系統開發，包含 FIDS API 串接與顯示、頻率 Scanner API 串接以及官網建置',
    technologies: ['C#', 'SQLite', 'Docker', 'Vue.js'],
    gradient: 'from-blue-600 to-indigo-600',
    link: 'https://twskywave.com'
  },
  {
    name: '個人網站',
    description: '使用響應式設計，為我自己的攝影作品建立展示平台',
    technologies: ['Vue.js', 'Tailwind CSS'],
    gradient: 'from-orange-600 to-yellow-600',
    link: 'https://www.pataimage.com'
  },
  {
    name: '星宇航空倉儲管理系統',
    description: '提供倉庫管理與庫存追蹤功能，以及海關相關保稅品管理',
    technologies: ['C#', 'MSSQL', 'Docker','Vue.js'],
    gradient: 'from-green-600 to-teal-600',
    link: ''
  },
  {
    name: '星宇航空機務保稅系統',
    description: '管理飛機零件的進出庫記錄，確保符合海關法規',
    technologies: ['C#', 'MSSQL', 'Docker','Vue.js'],
    gradient: 'from-green-600 to-teal-600',
    link: ''
  }
])
</script>