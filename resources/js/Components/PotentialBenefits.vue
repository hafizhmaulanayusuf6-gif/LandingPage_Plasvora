<script setup>
const benefitGroups = [
    {
        target: 'Untuk Kreator dan Pengrajin',
        description: 'Membantu menemukan inspirasi dan informasi material sebagai titik awal untuk mengembangkan kreasi.',
        icon: 'creator',
        highlights: [
            'Inspirasi ragam bentuk karya dari limbah plastik',
            'Pengetahuan karakteristik polimer (PET, HDPE, PP)',
            'Panduan langkah persiapan bahan baku'
        ]
    },
    {
        target: 'Untuk Pelaku Material Daur Ulang',
        description: 'Mendukung penemuan informasi mengenai material yang berpotensi dimanfaatkan oleh pihak lain.',
        icon: 'recycler',
        highlights: [
            'Eksplorasi katalog jenis dan kondisi material',
            'Pencatatan penawaran dan serah terima secara rapi',
            'Peluang kolaborasi dengan komunitas upcycling'
        ]
    }
];
</script>

<template>
    <section class="py-20 sm:py-28 bg-[#E6F7F0]/40 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- Section Header -->
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="inline-block px-3.5 py-1.5 rounded-full bg-[#E6F7F0] text-[#0D3B2E] text-xs sm:text-sm font-semibold tracking-wider uppercase mb-3 border border-[#4E9F85]/20">
                    KOLABORASI & DAMPAK
                </span>
                <h2 class="font-heading font-extrabold text-3xl sm:text-4xl lg:text-5xl text-[#0D3B2E] tracking-tight">
                    Ruang untuk Ide dan Kolaborasi.
                </h2>
                <p class="font-body text-base sm:text-lg text-[#5A6E65] mt-4 leading-relaxed">
                    Plasvora dirancang untuk mendukung eksplorasi ide pemanfaatan plastik dan penemuan bahan daur ulang.
                </p>
            </div>

            <!-- 2 Beneficial Persona Cards -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-10 max-w-5xl mx-auto">
                <div
                    v-for="group in benefitGroups"
                    :key="group.target"
                    class="p-8 sm:p-10 rounded-3xl bg-white border border-[#0D3B2E]/10 shadow-[0_15px_35px_rgba(13,59,46,0.06)] flex flex-col justify-between"
                >
                    <div>
                        <!-- Icon -->
                        <div class="w-14 h-14 rounded-2xl bg-[#E6F7F0] text-[#0D3B2E] flex items-center justify-center mb-6">
                            <svg v-if="group.icon === 'creator'" class="w-7 h-7 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"></path>
                            </svg>
                            <svg v-else class="w-7 h-7 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"></path>
                                <circle cx="9" cy="7" r="4"></circle>
                                <path d="M22 21v-2a4 4 0 0 0-3-3.87"></path>
                                <path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
                            </svg>
                        </div>

                        <!-- Target Persona Title -->
                        <h3 class="font-heading font-bold text-2xl text-[#0D3B2E]">
                            {{ group.target }}
                        </h3>

                        <!-- Core Description -->
                        <p class="font-body text-base text-[#5A6E65] mt-3 leading-relaxed">
                            {{ group.description }}
                        </p>

                        <!-- Highlights List -->
                        <ul class="mt-6 space-y-3 pt-6 border-t border-[#0D3B2E]/10">
                            <li
                                v-for="point in group.highlights"
                                :key="point"
                                class="flex items-start gap-3 text-sm text-[#0D3B2E]/80"
                            >
                                <svg class="w-5 h-5 text-[#4E9F85] shrink-0 mt-0.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"></path>
                                </svg>
                                <span>{{ point }}</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

