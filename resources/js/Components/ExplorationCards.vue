<script setup>
const explorationCards = [
    {
        title: 'Inspirasi Kreasi',
        description: 'Jelajahi berbagai ide untuk memberikan kemungkinan pemanfaatan baru pada plastik bekas.',
        ctaText: 'Jelajahi Inspirasi',
        ctaHref: '#fitur',
        category: 'Kreativitas & Ide',
        icon: 'bulb'
    },
    {
        title: 'Panduan Pemanfaatan',
        description: 'Kenali gambaran bahan dan tahapan yang diperlukan untuk memulai sebuah kreasi.',
        ctaText: 'Lihat Panduan',
        ctaHref: '#preview',
        category: 'Edukasi & Langkah',
        icon: 'steps'
    },
    {
        title: 'Material Daur Ulang',
        description: 'Jelajahi konsep penemuan bahan daur ulang untuk mendukung kegiatan kreasi.',
        ctaText: 'Kenali Material',
        ctaHref: '#preview',
        category: 'Katalog Bahan',
        icon: 'box'
    }
];
</script>

<template>
    <section id="eksplorasi" class="py-20 sm:py-28 bg-[#F8FAF9] relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- Section Header -->
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="inline-block px-3.5 py-1.5 rounded-full bg-[#E6F7F0] text-[#0D3B2E] text-xs sm:text-sm font-semibold tracking-wider uppercase mb-3">
                    EKSPLORASI PLASVORA
                </span>
                <h2 class="font-heading font-extrabold text-3xl sm:text-4xl lg:text-5xl text-[#0D3B2E] tracking-tight">
                    Jelajahi Peluang dari Plastik.
                </h2>
                <p class="font-body text-base sm:text-lg text-[#5A6E65] mt-4 leading-relaxed">
                    Pilih titik awal yang sesuai dengan kebutuhanmu.
                </p>
            </div>

            <!-- 3 Balanced Exploration Cards -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div
                    v-for="card in explorationCards"
                    :key="card.title"
                    class="flex flex-col justify-between p-8 rounded-3xl bg-white border border-[#0D3B2E]/10 shadow-[0_10px_30px_rgba(13,59,46,0.05)] hover:shadow-xl hover:border-[#4E9F85]/40 transition-all duration-300 group"
                >
                    <div>
                        <!-- Category Chip & Icon -->
                        <div class="flex items-center justify-between mb-6">
                            <span class="text-xs font-semibold text-[#4E9F85] uppercase tracking-wider bg-[#E6F7F0] px-3 py-1 rounded-full">
                                {{ card.category }}
                            </span>
                            <div class="w-10 h-10 rounded-xl bg-[#E6F7F0] flex items-center justify-center text-[#0D3B2E] group-hover:bg-[#4E9F85] group-hover:text-white transition-colors">
                                <svg v-if="card.icon === 'bulb'" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path>
                                </svg>
                                <svg v-else-if="card.icon === 'steps'" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4"></path>
                                </svg>
                                <svg v-else class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"></path>
                                </svg>
                            </div>
                        </div>

                        <!-- Card Title -->
                        <h3 class="font-heading font-bold text-xl sm:text-2xl text-[#0D3B2E] group-hover:text-[#4E9F85] transition-colors">
                            {{ card.title }}
                        </h3>

                        <!-- Card Description -->
                        <p class="font-body text-sm sm:text-base text-[#5A6E65] mt-3 leading-relaxed">
                            {{ card.description }}
                        </p>
                    </div>

                    <!-- Card Real CTA Action -->
                    <div class="pt-8">
                        <a
                            :href="card.ctaHref"
                            class="w-full min-h-[44px] px-6 py-3 rounded-xl bg-[#E6F7F0] text-[#0D3B2E] font-semibold text-sm hover:bg-[#4E9F85] hover:text-white transition-all duration-200 inline-flex items-center justify-center focus:outline-none focus:ring-2 focus:ring-[#4E9F85]"
                        >
                            {{ card.ctaText }}
                        </a>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

