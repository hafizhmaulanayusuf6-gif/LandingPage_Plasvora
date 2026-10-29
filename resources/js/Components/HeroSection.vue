<script setup>
import AppPhoneMockup from './AppPhoneMockup.vue';
</script>

<template>
    <section id="beranda" class="relative pt-28 sm:pt-36 pb-24 sm:pb-32 bg-gradient-to-b from-[#0D3B2E] via-[#0e3f32] to-[#0a2f25] text-white overflow-hidden">
        <!-- Organic Background Accents & Subtle Depth -->
        <div class="absolute -top-32 -left-32 w-96 h-96 rounded-full bg-[#4E9F85]/15 blur-3xl pointer-events-none"></div>
        <div class="absolute top-1/3 -right-24 w-80 h-80 rounded-full bg-[#E6F7F0]/10 blur-3xl pointer-events-none"></div>

        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-8 items-center">
                
                <!-- Left Hero Content (Columns 1 to 7) -->
                <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                    
                    <!-- Eyebrow Tag -->
                    <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-[#4E9F85]/20 border border-[#4E9F85]/30 text-[#E6F7F0] text-xs sm:text-sm font-semibold tracking-wider uppercase">
                        INOVASI UNTUK MASA DEPAN BERKELANJUTAN
                    </div>

                    <!-- Main Headline -->
                    <h1 class="font-heading font-extrabold text-3xl sm:text-5xl lg:text-6xl text-white tracking-tight leading-[1.15]">
                        Ubah Sampah Plastik Menjadi <span class="text-[#4E9F85]">Peluang Baru.</span>
                    </h1>

                    <!-- Description Body -->
                    <p class="font-body text-base sm:text-lg text-[#E6F7F0]/85 max-w-2xl mx-auto lg:mx-0 leading-relaxed">
                        Temukan inspirasi untuk memanfaatkan plastik bekas dan jelajahi potensi bahan daur ulang dalam satu platform.
                    </p>

                    <!-- Call To Action Buttons -->
                    <div class="pt-2 flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4">
                        <a
                            href="#fitur"
                            class="w-full sm:w-auto min-h-[48px] px-7 py-3.5 rounded-full bg-[#4E9F85] text-white font-semibold text-base hover:bg-[#3d836c] transition-all duration-200 shadow-lg shadow-[#0D3B2E]/40 inline-flex items-center justify-center focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-[#0D3B2E] focus:ring-[#4E9F85]"
                        >
                            Jelajahi Fitur
                        </a>
                        <a
                            href="#preview"
                            class="w-full sm:w-auto min-h-[48px] px-7 py-3.5 rounded-full bg-white/10 text-white font-semibold text-base border border-white/20 hover:bg-white/20 transition-all duration-200 inline-flex items-center justify-center focus:outline-none focus:ring-2 focus:ring-white/50"
                        >
                            Lihat Preview
                        </a>
                    </div>

                    <!-- Platform Scope Note -->
                    <div class="pt-4 flex items-center justify-center lg:justify-start gap-6 text-xs text-[#E6F7F0]/70">
                        <div class="flex items-center gap-2">
                            <svg class="w-4 h-4 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"></path>
                            </svg>
                            <span>Inspirasi Upcycling</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <svg class="w-4 h-4 text-[#4E9F85]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"></path>
                            </svg>
                            <span>Katalog Bahan Daur Ulang</span>
                        </div>
                    </div>
                </div>

                <!-- Right Hero Visual Mockup (Columns 8 to 12) -->
                <div class="lg:col-span-5 flex justify-center relative">
                    <!-- Glow halo behind mockup -->
                    <div class="absolute inset-0 bg-[#4E9F85]/20 blur-2xl rounded-full scale-95 pointer-events-none"></div>
                    
                    <AppPhoneMockup
                        image-src="/images/app-screens/beranda.jpg"
                        alt-text="Tampilan Aplikasi Mobile Plasvora Beranda"
                        badge-text="Preview Layar Aplikasi Mobile"
                        size="normal"
                    />
                </div>

            </div>
        </div>

        <!-- Wave Divider Bottom -->
        <div class="absolute bottom-0 left-0 right-0 w-full overflow-hidden leading-none pointer-events-none">
            <svg class="relative block w-full h-10 sm:h-16 text-[#F8FAF9]" viewBox="0 0 1200 120" preserveAspectRatio="none">
                <path d="M0,0 C150,90 350,-40 500,45 C650,130 900,10 1200,50 L1200,120 L0,120 Z" fill="currentColor"></path>
            </svg>
        </div>
    </section>
</template>

