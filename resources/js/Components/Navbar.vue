<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isMenuOpen = ref(false);
const isScrolled = ref(false);

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
    isMenuOpen.value = false;
};

const handleScroll = () => {
    isScrolled.value = window.scrollY > 20;
};

const handleKeyDown = (e) => {
    if (e.key === 'Escape' && isMenuOpen.value) {
        closeMenu();
    }
};

onMounted(() => {
    window.addEventListener('scroll', handleScroll, { passive: true });
    window.addEventListener('keydown', handleKeyDown);
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
    window.removeEventListener('keydown', handleKeyDown);
});

const navLinks = [
    { label: 'Beranda', href: '#beranda' },
    { label: 'Tentang', href: '#tentang' },
    { label: 'Fitur', href: '#fitur' },
    { label: 'Eksplorasi', href: '#eksplorasi' },
    { label: 'Preview', href: '#preview' }
];
</script>

<template>
    <header
        class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
        :class="[
            isScrolled
                ? 'bg-[#0D3B2E]/95 backdrop-blur-md shadow-md py-3 border-b border-[#4E9F85]/20'
                : 'bg-[#0D3B2E] py-4 sm:py-5 border-b border-[#4E9F85]/10'
        ]"
    >
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between">
                <!-- Brand Logo / Wordmark -->
                <a
                    href="#beranda"
                    class="flex items-center gap-2.5 group focus:outline-none focus:ring-2 focus:ring-[#4E9F85] rounded-lg p-1"
                >
                    <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-[#4E9F85] to-[#2E7A63] flex items-center justify-center text-white shadow-sm ring-1 ring-white/20">
                        <svg class="w-5 h-5 text-white" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M7 19H4.815a1.83 1.83 0 0 1-1.57-.881 1.785 1.785 0 0 1-.004-1.784L7.196 9.5"></path>
                            <path d="M11 19h8.2a1.8 1.8 0 0 0 1.571-.888 1.8 1.8 0 0 0-.005-1.78L16.8 9.5"></path>
                            <path d="M14.5 4.5 12 2l-2.5 2.5"></path>
                            <path d="M12 2v6.5"></path>
                        </svg>
                    </div>
                    <span class="font-heading font-extrabold text-xl sm:text-2xl tracking-tight text-white">
                        PLASVORA
                    </span>
                </a>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex items-center gap-1 lg:gap-2" aria-label="Navigasi Utama">
                    <a
                        v-for="link in navLinks"
                        :key="link.href"
                        :href="link.href"
                        class="px-3.5 py-2 text-sm font-medium text-[#E6F7F0]/90 hover:text-white hover:bg-white/10 rounded-lg transition-colors focus:outline-none focus:ring-2 focus:ring-[#4E9F85]"
                    >
                        {{ link.label }}
                    </a>
                </nav>

                <!-- Desktop CTA Button -->
                <div class="hidden md:flex items-center gap-3">
                    <a
                        href="#fitur"
                        class="inline-flex items-center justify-center px-5 py-2.5 text-sm font-semibold rounded-full bg-[#4E9F85] text-white hover:bg-[#3d836c] transition-all duration-200 shadow-sm focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-[#0D3B2E] focus:ring-[#4E9F85]"
                    >
                        Jelajahi Fitur
                    </a>
                </div>

                <!-- Mobile Menu Button -->
                <button
                    type="button"
                    class="md:hidden inline-flex items-center justify-center p-2.5 rounded-lg text-white hover:bg-white/10 focus:outline-none focus:ring-2 focus:ring-[#4E9F85]"
                    :aria-expanded="isMenuOpen"
                    aria-label="Toggle menu navigasi"
                    @click="toggleMenu"
                >
                    <svg
                        v-if="!isMenuOpen"
                        class="w-6 h-6"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                        stroke-width="2"
                    >
                        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                    <svg
                        v-else
                        class="w-6 h-6"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                        stroke-width="2"
                    >
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"></path>
                    </svg>
                </button>
            </div>
        </div>

        <!-- Mobile Drawer Navigation -->
        <transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="opacity-0 -translate-y-2"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition duration-150 ease-in"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 -translate-y-2"
        >
            <div
                v-if="isMenuOpen"
                class="md:hidden bg-[#0D3B2E] border-b border-[#4E9F85]/20 shadow-xl px-4 pt-2 pb-6"
            >
                <nav class="flex flex-col space-y-1" aria-label="Navigasi Mobile">
                    <a
                        v-for="link in navLinks"
                        :key="link.href"
                        :href="link.href"
                        class="px-4 py-3 min-h-[44px] text-base font-medium text-[#E6F7F0] hover:text-white hover:bg-white/10 rounded-lg transition-colors flex items-center"
                        @click="closeMenu"
                    >
                        {{ link.label }}
                    </a>
                    <div class="pt-3">
                        <a
                            href="#fitur"
                            class="w-full min-h-[44px] inline-flex items-center justify-center px-5 py-3 text-sm font-semibold rounded-full bg-[#4E9F85] text-white hover:bg-[#3d836c] transition-colors"
                            @click="closeMenu"
                        >
                            Jelajahi Fitur
                        </a>
                    </div>
                </nav>
            </div>
        </transition>
    </header>
</template>

