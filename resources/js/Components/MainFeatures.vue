<script setup>
import AppPhoneMockup from './AppPhoneMockup.vue';

const leftFeatures = [
    {
        title: 'Inspirasi Kreasi',
        description: 'Temukan ide untuk memanfaatkan plastik bekas menjadi benda yang berpotensi berguna.',
        icon: 'sparkle'
    },
    {
        title: 'Panduan Langkah demi Langkah',
        description: 'Pahami bahan yang diperlukan dan urutan pengerjaan sebuah kreasi.',
        icon: 'steps'
    },
    {
        title: 'Informasi Material',
        description: 'Kenali informasi dasar tentang jenis dan karakteristik material.',
        icon: 'info'
    }
];

const rightFeatures = [
    {
        title: 'Katalog Bahan Daur Ulang',
        description: 'Jelajahi konsep katalog material yang dapat dimanfaatkan.',
        icon: 'catalog'
    },
    {
        title: 'Informasi Produk',
        description: 'Kenali detail material dan informasi penjual jika tersedia.',
        icon: 'tag'
    },
    {
        title: 'Eksplorasi Berkelanjutan',
        description: 'Temukan kemungkinan pemanfaatan material dalam berbagai konteks.',
        icon: 'globe'
    }
];
</script>

<template>
    <section id="fitur" class="py-20 sm:py-28 bg-[#F8FAF9] relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- Section Header -->
            <div class="text-center max-w-3xl mx-auto mb-16 sm:mb-20">
                <span class="inline-block px-3.5 py-1.5 rounded-full bg-[#E6F7F0] text-[#0D3B2E] text-xs sm:text-sm font-semibold tracking-wider uppercase mb-3">
                    FITUR UNGGULAN
                </span>
                <h2 class="font-heading font-extrabold text-3xl sm:text-4xl lg:text-5xl text-[#0D3B2E] tracking-tight">
                    Semua Berawal dari Satu Ide.
                </h2>
                <p class="font-body text-base sm:text-lg text-[#5A6E65] mt-4 leading-relaxed">
                    Jelajahi inspirasi pemanfaatan plastik dan kenali potensi bahan daur ulang untuk mendukung kreasi yang lebih bertanggung jawab.
                </p>
            </div>

            <!-- Features Showcase Layout: 3 Columns on Desktop (Left Features - Phone Center - Right Features) -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-6 items-center">
                
                <!-- Left 3 Features (Desktop Col 1-4) -->
                <div class="lg:col-span-4 space-y-8 sm:space-y-10 order-2 lg:order-1">
                    <div
                        v-for="(feature, idx) in leftFeatures"
                        :key="feature.title"
                        class="p-6 rounded-2xl bg-white border border-[#0D3B2E]/5 shadow-xs hover:border-[#4E9F85]/30 hover:shadow-md transition-all duration-200 group"
                    >
                        <div class="flex items-start gap-4">
                            <div class="w-11 h-11 rounded-xl bg-[#E6F7F0] text-[#0D3B2E] flex items-center justify-center shrink-0 group-hover:bg-[#4E9F85] group-hover:text-white transition-colors duration-200">
                                <span class="font-heading font-bold text-sm">{{ idx + 1 }}</span>
                            </div>
                            <div>
                                <h3 class="font-heading font-bold text-lg text-[#0D3B2E] group-hover:text-[#4E9F85] transition-colors">
                                    {{ feature.title }}
                                </h3>
                                <p class="font-body text-sm text-[#5A6E65] mt-1.5 leading-relaxed">
                                    {{ feature.description }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Center Smartphone Showcase (Desktop Col 5-8) -->
                <div class="lg:col-span-4 flex justify-center order-1 lg:order-2 my-4 lg:my-0">
                    <div class="relative w-full flex justify-center">
                        <!-- Soft decorative circular ring -->
                        <div class="absolute inset-0 m-auto w-72 h-72 rounded-full bg-[#E6F7F0]/60 -z-10 blur-xl"></div>
                        
                        <AppPhoneMockup
                            image-src="/images/app-screens/analisis.jpg"
                            alt-text="Layar Fitur Analisis Plastik Plasvora"
                            badge-text="Fitur Analisis & Pemindaian AI"
                            size="normal"
                        />
                    </div>
                </div>

                <!-- Right 3 Features (Desktop Col 9-12) -->
                <div class="lg:col-span-4 space-y-8 sm:space-y-10 order-3">
                    <div
                        v-for="(feature, idx) in rightFeatures"
                        :key="feature.title"
                        class="p-6 rounded-2xl bg-white border border-[#0D3B2E]/5 shadow-xs hover:border-[#4E9F85]/30 hover:shadow-md transition-all duration-200 group"
                    >
                        <div class="flex items-start gap-4">
                            <div class="w-11 h-11 rounded-xl bg-[#E6F7F0] text-[#0D3B2E] flex items-center justify-center shrink-0 group-hover:bg-[#4E9F85] group-hover:text-white transition-colors duration-200">
                                <span class="font-heading font-bold text-sm">{{ idx + 4 }}</span>
                            </div>
                            <div>
                                <h3 class="font-heading font-bold text-lg text-[#0D3B2E] group-hover:text-[#4E9F85] transition-colors">
                                    {{ feature.title }}
                                </h3>
                                <p class="font-body text-sm text-[#5A6E65] mt-1.5 leading-relaxed">
                                    {{ feature.description }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

        </div>
    </section>
</template>

