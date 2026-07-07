<script setup>
import { Icon } from '@iconify/vue'

const tacos = [
  {
    name: "Lolita's Taco Shop",
    area: 'Ocean Beach',
    rating: 4.8,
    reviews: 1240,
    tags: ['카르네아사다', '캘리포니아'],
    desc: '클래식 카르네 아사다 타코 원탑. 줄 서서 먹을 각.',
    badge: 'TOP PICK',
    bg: 'bg-fuchsia-400',
    rotate: '-rotate-2',
  },
  {
    name: 'El Zarape',
    area: 'North Park',
    rating: 4.6,
    reviews: 860,
    tags: ['수제토르티야', '찐멕시칸'],
    desc: '토르티야부터 수제로 승부보는 정통 멕시칸 감성.',
    badge: 'HOT',
    badgeIcon: 'mdi:fire',
    bg: 'bg-lime-300',
    rotate: 'rotate-2',
  },
  {
    name: 'Las Cuatro Milpas',
    area: 'Barrio Logan',
    rating: 4.9,
    reviews: 2100,
    tags: ['레전드', 'since 1933'],
    desc: '1933년생 원조 맛집. 안 가본 사람은 있어도 한번 간 사람은 없음.',
    badge: 'LEGEND',
    bg: 'bg-cyan-300',
    rotate: '-rotate-1',
  },
  {
    name: 'The Taco Stand',
    area: 'La Jolla',
    rating: 4.7,
    reviews: 1560,
    tags: ['티후아나스타일', '핵인기'],
    desc: '티후아나 감성 그대로. 웨이팅 각오하고 가야함.',
    badge: 'NEW',
    bg: 'bg-orange-300',
    rotate: 'rotate-1',
  },
]

const stats = [
  { icon: 'fluent-emoji-flat:taco', label: '엄선 맛집', value: `${tacos.length}곳` },
  { icon: 'mdi:star', label: '평균 평점', value: '4.75' },
  { icon: 'mdi:comment-text-outline', label: '누적 리뷰', value: '5.7K+' },
]

const marqueeItems = [
  { icon: 'fluent-emoji-flat:taco', text: 'SAN DIEGO 찐맛집 모음' },
  { icon: 'mdi:fire', text: '지금 안가면 손해' },
  { icon: 'mdi:star', text: '로컬 인증 완료' },
  { icon: 'mdi:chili-hot', text: '웨이팅 각오 필수' },
]
</script>

<template>
  <div class="min-h-screen overflow-x-hidden bg-yellow-200 font-sans text-stone-900">
    <!-- Nav -->
    <nav class="sticky top-0 z-50 border-b-4 border-black bg-yellow-200/90 backdrop-blur">
      <div class="mx-auto flex max-w-6xl items-center justify-between px-5 py-3">
        <div class="flex items-center gap-2">
          <span class="flex h-10 w-10 items-center justify-center rounded-full border-4 border-black bg-fuchsia-400 shadow-[3px_3px_0_0_#000]">
            <Icon icon="fluent-emoji-flat:taco" class="h-5.5 w-5.5" />
          </span>
          <span class="font-display text-lg">맛도리 타코</span>
        </div>
        <a
          href="#taco-list"
          class="rounded-full border-4 border-black bg-lime-300 px-4 py-2 text-sm font-bold shadow-[4px_4px_0_0_#000] transition active:translate-x-1 active:translate-y-1 active:shadow-none"
        >
          맛집 보러가기
        </a>
      </div>
    </nav>

    <!-- Marquee -->
    <div class="overflow-hidden border-b-4 border-black bg-black py-2.5">
      <div class="flex w-max animate-marquee gap-10 whitespace-nowrap">
        <span
          v-for="n in 2"
          :key="n"
          class="flex items-center gap-10 text-sm font-bold tracking-wide text-yellow-300"
        >
          <span v-for="item in marqueeItems" :key="item.text" class="flex items-center gap-2">
            <Icon :icon="item.icon" class="h-4 w-4" />
            {{ item.text }}
            <span class="text-fuchsia-400">•</span>
          </span>
        </span>
      </div>
    </div>

    <!-- Hero -->
    <header class="relative overflow-hidden px-5 pt-16 pb-24">
      <div class="pointer-events-none absolute -top-10 -left-16 h-64 w-64 animate-blob rounded-full bg-fuchsia-400 opacity-60 blur-3xl"></div>
      <div class="pointer-events-none absolute top-20 -right-10 h-72 w-72 animate-blob rounded-full bg-cyan-300 opacity-60 blur-3xl [animation-delay:2s]"></div>

      <div class="relative mx-auto flex max-w-3xl flex-col items-center text-center">
        <div
          class="mb-6 flex h-28 w-28 items-center justify-center rounded-full border-4 border-black bg-white shadow-[6px_6px_0_0_#000]"
        >
          <Icon icon="fluent-emoji-flat:taco" class="h-16 w-16 animate-taco-wiggle" />
        </div>

        <span class="mb-4 inline-flex items-center gap-1 rounded-full border-2 border-black bg-white px-3 py-1 text-xs font-bold">
          <Icon icon="mdi:map-marker" class="h-3.5 w-3.5" />
          SAN DIEGO, CA
        </span>

        <h1 class="flex flex-wrap items-center justify-center gap-x-3 font-display text-5xl leading-tight sm:text-6xl">
          <span class="w-full">찐맛집만</span>
          <span class="bg-fuchsia-400 px-2">모았다</span>
          <Icon icon="fluent-emoji-flat:taco" class="h-10 w-10 sm:h-12 sm:w-12" />
        </h1>
        <p class="mt-5 max-w-md text-lg font-semibold text-stone-700">
          샌디에고 로컬 인정 타코 맛집, 어 인정.<br />
          가짜 맛집 리스트 아니고 찐임.
        </p>

        <div class="mt-9 flex flex-wrap items-center justify-center gap-4">
          <a
            href="#taco-list"
            class="flex items-center gap-2 rounded-full border-4 border-black bg-fuchsia-400 px-7 py-3 font-display text-base shadow-[6px_6px_0_0_#000] transition hover:-translate-y-0.5 active:translate-x-1.5 active:translate-y-1.5 active:shadow-none"
          >
            <Icon icon="mdi:silverware-fork-knife" class="h-5 w-5" />
            맛집 보기
          </a>
          <a
            href="#"
            class="flex items-center gap-2 rounded-full border-4 border-black bg-white px-7 py-3 font-display text-base shadow-[6px_6px_0_0_#000] transition hover:-translate-y-0.5 active:translate-x-1.5 active:translate-y-1.5 active:shadow-none"
          >
            <Icon icon="mdi:google-maps" class="h-5 w-5" />
            지도 보기
          </a>
        </div>
      </div>
    </header>

    <!-- Stats -->
    <section class="mx-auto -mt-10 mb-6 max-w-4xl px-5">
      <div class="grid grid-cols-3 gap-3 rounded-3xl border-4 border-black bg-white p-5 shadow-[8px_8px_0_0_#000] sm:gap-6 sm:p-7">
        <div v-for="stat in stats" :key="stat.label" class="flex flex-col items-center gap-1 text-center">
          <span class="flex h-9 w-9 items-center justify-center rounded-full border-2 border-black bg-lime-300">
            <Icon :icon="stat.icon" class="h-4.5 w-4.5" />
          </span>
          <span class="font-display text-xl sm:text-2xl">{{ stat.value }}</span>
          <span class="text-xs font-semibold text-stone-500">{{ stat.label }}</span>
        </div>
      </div>
    </section>

    <!-- Taco list -->
    <main id="taco-list" class="mx-auto max-w-5xl px-5 py-24">
      <div class="mb-14 text-center">
        <h2 class="flex items-center justify-center gap-2 font-display text-3xl sm:text-4xl">
          이 정도는 가야함
          <Icon icon="mdi:hand-clap" class="h-8 w-8 text-fuchsia-500 sm:h-9 sm:w-9" />
        </h2>
        <p class="mt-3 font-semibold text-stone-600">발로 뛰어서 고른 샌디에고 최애 타코</p>
      </div>

      <div class="grid gap-8 sm:grid-cols-2">
        <article
          v-for="taco in tacos"
          :key="taco.name"
          class="group relative overflow-visible rounded-3xl border-4 border-black bg-white shadow-[8px_8px_0_0_#000] transition duration-300"
          :class="[taco.rotate, 'hover:rotate-0 hover:-translate-y-1 hover:shadow-[12px_12px_0_0_#000]']"
        >
          <span
            class="absolute -top-4 -right-3 z-10 flex items-center gap-1 rotate-6 rounded-full border-2 border-black bg-black px-3 py-1 text-xs font-bold text-yellow-300 shadow-[3px_3px_0_0_#000]"
          >
            <Icon v-if="taco.badgeIcon" :icon="taco.badgeIcon" class="h-3.5 w-3.5" />
            {{ taco.badge }}
          </span>

          <div class="relative flex h-32 items-center justify-center border-b-4 border-black" :class="taco.bg">
            <Icon icon="fluent-emoji-flat:taco" class="h-14 w-14 drop-shadow transition group-hover:scale-110 group-hover:-rotate-6" />
            <span class="absolute top-3 left-3 flex items-center gap-1 rounded-full border-2 border-black bg-white px-2.5 py-1 text-xs font-bold">
              <Icon icon="mdi:star" class="h-3.5 w-3.5 text-amber-500" />
              {{ taco.rating }}
            </span>
          </div>

          <div class="p-6">
            <h3 class="font-display text-xl">{{ taco.name }}</h3>
            <p class="mt-1.5 flex items-center gap-1 text-sm font-semibold text-stone-500">
              <Icon icon="mdi:map-marker-outline" class="h-4 w-4" />
              {{ taco.area }}
              <span class="mx-1 text-stone-300">·</span>
              <Icon icon="mdi:comment-text-outline" class="h-4 w-4" />
              리뷰 {{ taco.reviews.toLocaleString() }}
            </p>
            <p class="mt-3 font-medium text-stone-700">{{ taco.desc }}</p>
            <div class="mt-4 flex flex-wrap gap-2">
              <span
                v-for="tag in taco.tags"
                :key="tag"
                class="rounded-full border-2 border-black bg-yellow-200 px-3 py-1 text-xs font-bold"
              >
                #{{ tag }}
              </span>
            </div>
          </div>
        </article>
      </div>
    </main>

    <!-- CTA banner -->
    <section class="px-5 pb-24">
      <div class="mx-auto flex max-w-4xl flex-col items-center gap-5 rounded-3xl border-4 border-black bg-fuchsia-400 p-10 text-center shadow-[8px_8px_0_0_#000]">
        <h3 class="flex items-center justify-center gap-2 font-display text-2xl sm:text-3xl">
          아직도 고민중? 그냥 가
          <Icon icon="fluent-emoji-flat:taco" class="h-8 w-8" />
        </h3>
        <p class="font-semibold text-stone-900/80">인생 타코는 생각보다 가까이 있음</p>
        <a
          href="#taco-list"
          class="flex items-center gap-2 rounded-full border-4 border-black bg-white px-7 py-3 font-display transition hover:-translate-y-0.5 active:translate-x-1.5 active:translate-y-1.5 active:shadow-none shadow-[6px_6px_0_0_#000]"
        >
          <Icon icon="mdi:fire" class="h-5 w-5 text-fuchsia-500" />
          맛집 다시 보기
        </a>
      </div>
    </section>

    <footer class="border-t-4 border-black bg-black py-10 text-yellow-300">
      <div class="mx-auto flex max-w-5xl flex-col items-center gap-3 px-5 text-center">
        <div class="flex items-center gap-2 font-display text-lg">
          <Icon icon="fluent-emoji-flat:taco" class="h-5.5 w-5.5" />
          맛도리 타코
        </div>
        <p class="flex items-center gap-1.5 text-sm font-semibold text-yellow-300/70">
          &copy; 2026 맛도리 타코. Made with
          <Icon icon="fluent-emoji-flat:taco" class="h-4 w-4" />
          in San Diego.
        </p>
      </div>
    </footer>
  </div>
</template>
