<script setup>
const summaryItems = [
    {
        title: 'Inspirasi Upcycling',
        description: 'Temukan ide kreatif untuk memanfaatkan plastik bekas.',
        icon: 'lightbulb'
    },
    {
        title: 'Panduan Kreasi',
        description: 'Pelajari bahan dan langkah pengerjaan secara terarah.',
        icon: 'book'
    },
    {
        title: 'Eksplorasi Material',
        description: 'Kenali bahan daur ulang untuk berbagai kebutuhan kreasi.',
        icon: 'cube'
    },
    {
        title: 'Dukungan Ekonomi Sirkular',
        description: 'Temukan peluang pemanfaatan material yang lebih bertanggung jawab.',
        icon: 'recycle'
    }
];
</script>

<template>
    <section class="relative z-20 -mt-8 sm:-mt-14 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="bg-white rounded-3xl p-6 sm:p-8 shadow-[0_20px_50px_rgba(13,59,46,0.08)] border border-[#0D3B2E]/10">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 lg:gap-8 divide-y sm:divide-y-0 sm:divide-x divide-[#0D3B2E]/10">
                <div
                    v-for="(item, idx) in summaryItems"
                    :key="item.title"
                    class="flex flex-col pt-4 sm:pt-0"
                    :class="{ 'sm:pl-6 lg:pl-8': idx > 0 }"
                >
                    <div class="w-12 h-12 rounded-2xl bg-[#E6F7F0] text-[#0D3B2E] flex items-center justify-center mb-4 transition-transform duration-200 group-hover:scale-105">
                        <!-- Icon 1: Inspirasi Upcycling -->
                        <svg v-if="item.icon === 'lightbulb'" class="w-6 h-6 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M15 14c.2-1 .7-1.7 1.5-2.5 1-.9 1.5-2.2 1.5-3.5A6 6 0 0 0 6 8c0 1 .2 2.2 1.5 3.5.7.7 1.3 1.5 1.5 2.5"></path>
                            <path d="M9 18h6"></path>
                            <path d="M10 22h4"></path>
                        </svg>
                        <!-- Icon 2: Panduan Kreasi -->
                        <svg v-else-if="item.icon === 'book'" class="w-6 h-6 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M4 19.5v-15A2.5 2.5 0 0 1 6.5 2H20v20H6.5a2.5 2.5 0 0 1-2.5-2.5Z"></path>
                            <path d="M6 6h10"></path>
                            <path d="M6 10h10"></path>
                        </svg>
                        <!-- Icon 3: Eksplorasi Material -->
                        <svg v-else-if="item.icon === 'cube'" class="w-6 h-6 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path>
                            <polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline>
                            <line x1="12" y1="22.08" x2="12" y2="12"></line>
                        </svg>
                        <!-- Icon 4: Sirkularitas -->
                        <svg v-else class="w-6 h-6 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M7 19H4.815a1.83 1.83 0 0 1-1.57-.881 1.785 1.785 0 0 1-.004-1.784L7.196 9.5"></path>
                            <path d="M11 19h8.2a1.8 1.8 0 0 0 1.571-.888 1.8 1.8 0 0 0-.005-1.78L16.8 9.5"></path>
                            <path d="M14.5 4.5 12 2l-2.5 2.5"></path>
                            <path d="M12 2v6.5"></path>
                        </svg>
                    </div>

                    <h3 class="font-heading font-bold text-base sm:text-lg text-[#0D3B2E]">
                        {{ item.title }}
                    </h3>
                    <p class="font-body text-xs sm:text-sm text-[#5A6E65] mt-1.5 leading-relaxed">
                        {{ item.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

