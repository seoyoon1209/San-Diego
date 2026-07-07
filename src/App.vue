<script setup>
import { Icon } from '@iconify/vue'

const tacos = [
  {
    name: "Lolita's Taco Shop",
    area: 'Ocean Beach',
    rating: 4.8,
    reviews: 1240,
    tags: ['카르네 아사다', '캘리포니아 스타일'],
    desc: '클래식한 캘리포니아 스타일 카르네 아사다 타코로 유명한 로컬 명소.',
    color: 'from-orange-400 to-rose-400',
  },
  {
    name: 'El Zarape',
    area: 'North Park',
    rating: 4.6,
    reviews: 860,
    tags: ['수제 토르티야', '정통 멕시칸'],
    desc: '수제 토르티야와 신선한 재료로 만든 정통 멕시칸 타코.',
    color: 'from-amber-400 to-orange-500',
  },
  {
    name: 'Las Cuatro Milpas',
    area: 'Barrio Logan',
    rating: 4.9,
    reviews: 2100,
    tags: ['전통 맛집', 'since 1933'],
    desc: '1933년부터 이어온 전통, 바리오 로건의 전설적인 타코 가게.',
    color: 'from-rose-400 to-red-500',
  },
  {
    name: 'The Taco Stand',
    area: 'La Jolla',
    rating: 4.7,
    reviews: 1560,
    tags: ['티후아나 스타일', '인기 맛집'],
    desc: '티후아나 스타일 타코를 미국에 처음 소개한 곳으로 유명.',
    color: 'from-yellow-400 to-amber-500',
  },
]

const stats = [
  { icon: 'mdi:taco', label: '엄선한 맛집', value: `${tacos.length}곳` },
  { icon: 'mdi:star', label: '평균 평점', value: '4.75' },
  { icon: 'mdi:comment-text-outline', label: '누적 리뷰', value: '5.7K+' },
]
</script>

<template>
  <div class="min-h-screen bg-stone-50 text-stone-800">
    <!-- Nav -->
    <nav class="sticky top-0 z-50 border-b border-stone-200/80 bg-white/80 backdrop-blur-md">
      <div class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
        <div class="flex items-center gap-2 font-bold text-stone-900">
          <Icon icon="mdi:taco" class="h-7 w-7 text-orange-500" />
          <span class="text-lg">맛도리 타코</span>
        </div>
        <a
          href="#taco-list"
          class="rounded-full bg-orange-500 px-5 py-2 text-sm font-semibold text-white shadow-sm shadow-orange-200 transition hover:bg-orange-600"
        >
          맛집 둘러보기
        </a>
      </div>
    </nav>

    <!-- Hero -->
    <header class="relative overflow-hidden bg-gradient-to-b from-orange-500 via-orange-400 to-stone-50">
      <div class="pointer-events-none absolute -top-24 -left-24 h-72 w-72 rounded-full bg-white/10 blur-3xl"></div>
      <div class="pointer-events-none absolute top-10 right-0 h-96 w-96 rounded-full bg-amber-300/30 blur-3xl"></div>

      <div class="relative mx-auto flex max-w-3xl flex-col items-center px-6 pt-20 pb-28 text-center text-white">
        <div class="mb-6 flex h-28 w-28 items-center justify-center rounded-full bg-white/15 shadow-inner ring-1 ring-white/30">
          <Icon icon="mdi:taco" class="h-16 w-16 animate-taco-wiggle text-white drop-shadow" />
        </div>
        <p class="mb-3 flex items-center gap-1.5 text-sm font-medium tracking-wide text-orange-50/90">
          <Icon icon="mdi:map-marker" class="h-4 w-4" />
          SAN DIEGO, CALIFORNIA
        </p>
        <h1 class="text-4xl font-extrabold tracking-tight sm:text-5xl">맛도리 타코</h1>
        <p class="mt-4 max-w-lg text-lg text-orange-50/95">
          샌디에고 로컬들이 인정한, 진짜 맛있는 타코 집만 엄선했어요
        </p>

        <div class="mt-9 flex flex-wrap items-center justify-center gap-3">
          <a
            href="#taco-list"
            class="flex items-center gap-2 rounded-full bg-stone-900 px-7 py-3 font-semibold text-white transition hover:-translate-y-0.5 hover:shadow-xl"
          >
            <Icon icon="mdi:silverware-fork-knife" class="h-5 w-5" />
            타코 맛집 보기
          </a>
          <a
            href="#"
            class="flex items-center gap-2 rounded-full bg-white/15 px-7 py-3 font-semibold text-white ring-1 ring-white/40 backdrop-blur transition hover:bg-white/25"
          >
            <Icon icon="mdi:google-maps" class="h-5 w-5" />
            지도로 보기
          </a>
        </div>
      </div>

      <!-- wave -->
      <svg viewBox="0 0 1440 80" class="relative block w-full text-stone-50" preserveAspectRatio="none">
        <path fill="currentColor" d="M0,32L80,42.7C160,53,320,75,480,74.7C640,75,800,53,960,42.7C1120,32,1280,32,1360,32L1440,32L1440,80L0,80Z" />
      </svg>
    </header>

    <!-- Stats -->
    <section class="mx-auto -mt-14 mb-4 max-w-4xl px-6">
      <div class="grid grid-cols-3 gap-4 rounded-2xl bg-white p-6 shadow-lg shadow-orange-100 ring-1 ring-stone-100">
        <div v-for="stat in stats" :key="stat.label" class="flex flex-col items-center gap-1 text-center">
          <Icon :icon="stat.icon" class="h-6 w-6 text-orange-500" />
          <span class="text-xl font-bold text-stone-900">{{ stat.value }}</span>
          <span class="text-xs text-stone-500">{{ stat.label }}</span>
        </div>
      </div>
    </section>

    <!-- Taco list -->
    <main id="taco-list" class="mx-auto max-w-5xl px-6 py-20">
      <div class="mb-10 text-center">
        <h2 class="text-3xl font-bold text-stone-900">추천 타코 집</h2>
        <p class="mt-2 text-stone-500">직접 발로 뛰며 고른 샌디에고 최고의 타코 맛집</p>
      </div>

      <div class="grid gap-6 sm:grid-cols-2">
        <article
          v-for="taco in tacos"
          :key="taco.name"
          class="group overflow-hidden rounded-2xl bg-white shadow-sm ring-1 ring-stone-100 transition hover:-translate-y-1 hover:shadow-xl"
        >
          <div
            class="relative flex h-32 items-center justify-center bg-gradient-to-br"
            :class="taco.color"
          >
            <Icon icon="mdi:taco" class="h-14 w-14 text-white/90 transition group-hover:scale-110 group-hover:-rotate-6" />
            <span class="absolute top-3 right-3 flex items-center gap-1 rounded-full bg-white/90 px-2.5 py-1 text-xs font-bold text-stone-800">
              <Icon icon="mdi:star" class="h-3.5 w-3.5 text-amber-500" />
              {{ taco.rating }}
            </span>
          </div>

          <div class="p-6">
            <div class="mb-1 flex items-center justify-between">
              <h3 class="text-xl font-bold text-stone-900">{{ taco.name }}</h3>
            </div>
            <p class="mb-3 flex items-center gap-1 text-sm text-stone-500">
              <Icon icon="mdi:map-marker-outline" class="h-4 w-4" />
              {{ taco.area }}
              <span class="mx-1 text-stone-300">·</span>
              <Icon icon="mdi:comment-text-outline" class="h-4 w-4" />
              리뷰 {{ taco.reviews.toLocaleString() }}
            </p>
            <p class="mb-4 text-stone-600">{{ taco.desc }}</p>
            <div class="flex flex-wrap gap-2">
              <span
                v-for="tag in taco.tags"
                :key="tag"
                class="rounded-full bg-orange-50 px-3 py-1 text-xs font-medium text-orange-600"
              >
                #{{ tag }}
              </span>
            </div>
          </div>
        </article>
      </div>
    </main>

    <footer class="border-t border-stone-200 bg-white py-10">
      <div class="mx-auto flex max-w-5xl flex-col items-center gap-4 px-6 text-center">
        <div class="flex items-center gap-2 font-bold text-stone-900">
          <Icon icon="mdi:taco" class="h-5 w-5 text-orange-500" />
          맛도리 타코
        </div>
        <p class="text-sm text-stone-400">&copy; 2026 맛도리 타코. Made with 🌮 in San Diego.</p>
      </div>
    </footer>
  </div>
</template>
