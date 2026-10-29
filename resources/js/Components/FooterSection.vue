<script setup>
const footerNav = [
    { label: 'Beranda', href: '#beranda' },
    { label: 'Tentang', href: '#tentang' },
    { label: 'Fitur', href: '#fitur' },
    { label: 'Eksplorasi', href: '#eksplorasi' },
    { label: 'Preview', href: '#preview' }
];
</script>

<template>
    <footer class="bg-[#09261E] text-white border-t border-[#4E9F85]/20 py-14 sm:py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-12 gap-10 items-start">
                
                <!-- Brand Info (Col 1 to 6) -->
                <div class="md:col-span-6 space-y-4">
                    <a href="#beranda" class="inline-flex items-center gap-2.5 group">
                        <div class="w-8 h-8 rounded-xl bg-[#4E9F85] flex items-center justify-center text-white">
                            <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="M7 19H4.815a1.83 1.83 0 0 1-1.57-.881 1.785 1.785 0 0 1-.004-1.784L7.196 9.5"></path>
                                <path d="M11 19h8.2a1.8 1.8 0 0 0 1.571-.888 1.8 1.8 0 0 0-.005-1.78L16.8 9.5"></path>
                                <path d="M14.5 4.5 12 2l-2.5 2.5"></path>
                                <path d="M12 2v6.5"></path>
                            </svg>
                        </div>
                        <span class="font-heading font-extrabold text-xl tracking-tight text-white">
                            PLASVORA
                        </span>
                    </a>
                    <p class="font-body text-sm text-[#E6F7F0]/70 max-w-sm leading-relaxed">
                        Platform sirkularitas digital bertema lingkungan yang berfokus pada inspirasi pemanfaatan sampah plastik dan penemuan bahan daur ulang.
                    </p>
                </div>

                <!-- Section Navigation Links (Col 7 to 9) -->
                <div class="md:col-span-3 space-y-3">
                    <h3 class="font-heading font-semibold text-sm text-[#E6F7F0] uppercase tracking-wider">
                        Navigasi Bagian
                    </h3>
                    <ul class="space-y-2 text-sm text-[#E6F7F0]/75">
                        <li v-for="item in footerNav" :key="item.href">
                            <a :href="item.href" class="hover:text-white hover:underline transition-colors">
                                {{ item.label }}
                            </a>
                        </li>
                    </ul>
                </div>

                <!-- Product Focus (Col 10 to 12) -->
                <div class="md:col-span-3 space-y-3">
                    <h3 class="font-heading font-semibold text-sm text-[#E6F7F0] uppercase tracking-wider">
                        Fokus Utama
                    </h3>
                    <ul class="space-y-2 text-sm text-[#E6F7F0]/75">
                        <li>Inspirasi Upcycling Plastik</li>
                        <li>Panduan Langkah Kreasi</li>
                        <li>Katalog Material Daur Ulang</li>
                        <li>Eksplorasi Ekonomi Sirkular</li>
                    </ul>
                </div>

            </div>

            <!-- Bottom Copyright Bar -->
            <div class="mt-12 pt-8 border-t border-white/10 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs text-[#E6F7F0]/60">
                <p>
                    &copy; 2026 Plasvora. Seluruh hak cipta dilindungi.
                </p>
                <p>
                    Inisiatif digital untuk mendukung pemanfaatan plastik bertanggung jawab.
                </p>
            </div>
        </div>
    </footer>
</template>

