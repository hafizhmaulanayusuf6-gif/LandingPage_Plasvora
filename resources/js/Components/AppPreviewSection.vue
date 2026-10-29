<script setup>
import { ref } from 'vue';
import AppPhoneMockup from './AppPhoneMockup.vue';

const activeTab = ref(0);

const screens = [
    {
        id: 'beranda',
        tabName: 'Beranda',
        title: 'Beranda Aplikasi',
        description: 'Pusat navigasi utama dengan rangkuman kontribusi sirkularitas, pemindaian cepat, dan rekomendasi material terkini.',
        imageSrc: '/images/app-screens/beranda.jpg',
        badge: 'Layar Beranda'
    },
    {
        id: 'analisis',
        tabName: 'Analisis AI',
        title: 'Analisis Plastik Berbasis AI',
        description: 'Fitur pemindaian foto material untuk mengenali tipe polimer (PET, HDPE, PP), estimasi berat, dan kondisi kebersihan.',
        imageSrc: '/images/app-screens/analisis.jpg',
        badge: 'Computer Vision V2.4'
    },
    {
        id: 'marketplace',
        tabName: 'Marketplace Material',
        title: 'Katalog Bahan Daur Ulang',
        description: 'Eksplorasi material yang tersedia dari berbagai sumber seperti tutup botol HDPE, serpihan PET, dan wadah kemasan siap pakai.',
        imageSrc: '/images/app-screens/marketplace.jpg',
        badge: 'Katalog Daur Ulang'
    },
    {
        id: 'aktivitas',
        tabName: 'Jejak Aktivitas',
        title: 'Verified Material Journey',
        description: 'Pencatatan siklus pergerakan material mulai dari penawaran, proses pengiriman, hingga konfirmasi pemanfaatan nyata.',
        imageSrc: '/images/app-screens/aktivitas.jpg',
        badge: 'Jejak & Serah Terima'
    }
];
</script>

<template>
    <section id="preview" class="py-20 sm:py-28 bg-[#F8FAF9] relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- Section Header -->
            <div class="text-center max-w-3xl mx-auto mb-12 sm:mb-16">
                <span class="inline-block px-3.5 py-1.5 rounded-full bg-[#E6F7F0] text-[#0D3B2E] text-xs sm:text-sm font-semibold tracking-wider uppercase mb-3 border border-[#4E9F85]/20">
                    PREVIEW APLIKASI
                </span>
                <h2 class="font-heading font-extrabold text-3xl sm:text-4xl lg:text-5xl text-[#0D3B2E] tracking-tight">
                    Pengalaman Aplikasi Plasvora.
                </h2>
                <p class="font-body text-base sm:text-lg text-[#5A6E65] mt-4 leading-relaxed">
                    Pilih tab di bawah untuk melihat tampilan antarmuka aplikasi pada setiap alur utama.
                </p>

                <!-- Interactive Screen Selector Pills -->
                <div class="mt-8 flex flex-wrap justify-center gap-2 sm:gap-3" role="tablist">
                    <button
                        v-for="(screen, idx) in screens"
                        :key="screen.id"
                        type="button"
                        role="tab"
                        :aria-selected="activeTab === idx"
                        class="min-h-[44px] px-5 py-2.5 rounded-full text-sm font-medium transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-[#4E9F85]"
                        :class="[
                            activeTab === idx
                                ? 'bg-[#0D3B2E] text-white shadow-sm'
                                : 'bg-white text-[#5A6E65] hover:bg-[#E6F7F0] hover:text-[#0D3B2E] border border-[#0D3B2E]/10'
                        ]"
                        @click="activeTab = idx"
                    >
                        {{ screen.tabName }}
                    </button>
                </div>
            </div>

            <!-- Preview Card Showcase -->
            <div class="max-w-5xl mx-auto bg-white rounded-3xl p-6 sm:p-12 border border-[#0D3B2E]/10 shadow-[0_20px_50px_rgba(13,59,46,0.06)]">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-12 items-center">
                    
                    <!-- Left: Details of the Active Screen -->
                    <div class="lg:col-span-6 space-y-5 text-center lg:text-left">
                        <span class="inline-block px-3 py-1 rounded-md bg-[#E6F7F0] text-[#4E9F85] text-xs font-semibold uppercase tracking-wider">
                            {{ screens[activeTab].badge }}
                        </span>
                        <h3 class="font-heading font-bold text-2xl sm:text-3xl text-[#0D3B2E]">
                            {{ screens[activeTab].title }}
                        </h3>
                        <p class="font-body text-base text-[#5A6E65] leading-relaxed">
                            {{ screens[activeTab].description }}
                        </p>

                        <div class="pt-4">
                            <a
                                href="#fitur"
                                class="inline-flex items-center gap-2 text-sm font-semibold text-[#4E9F85] hover:text-[#0D3B2E] transition-colors focus:outline-none focus:ring-2 focus:ring-[#4E9F85] rounded-md px-1"
                            >
                                <span>Lihat detail fitur terkait</span>
                                <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"></path>
                                </svg>
                            </a>
                        </div>
                    </div>

                    <!-- Right: Responsive Smartphone Mockup displaying the chosen screen -->
                    <div class="lg:col-span-6 flex justify-center">
                        <AppPhoneMockup
                            :key="screens[activeTab].id"
                            :image-src="screens[activeTab].imageSrc"
                            :alt-text="screens[activeTab].title"
                            :badge-text="screens[activeTab].badge"
                            size="normal"
                        />
                    </div>

                </div>
            </div>

        </div>
    </section>
</template>

