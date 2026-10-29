<script setup>
import { ref } from 'vue';

const props = defineProps({
    imageSrc: {
        type: String,
        default: '/images/app-screens/beranda.jpg'
    },
    altText: {
        type: String,
        default: 'Plasvora Mobile App Preview'
    },
    badgeText: {
        type: String,
        default: ''
    },
    size: {
        type: String,
        default: 'normal' // 'small', 'normal', 'large'
    }
});

const imageError = ref(false);

const handleImageError = () => {
    imageError.value = true;
};
</script>

<template>
    <div class="relative mx-auto flex flex-col items-center select-none" :class="{
        'max-w-[280px] sm:max-w-[300px]': size === 'small',
        'max-w-[310px] sm:max-w-[340px]': size === 'normal',
        'max-w-[340px] sm:max-w-[380px]': size === 'large',
    }">
        <!-- Phone Outer Shell with Realistic Shadow and Bezel -->
        <div class="relative w-full rounded-[48px] p-3 bg-gradient-to-b from-[#1a2d24] via-[#0D3B2E] to-[#08221a] shadow-[0_25px_60px_-15px_rgba(13,59,46,0.35),0_12px_24px_-8px_rgba(0,0,0,0.2)] border border-[#4E9F85]/20 ring-1 ring-white/10">
            
            <!-- Side Buttons -->
            <div class="absolute -left-[3px] top-28 w-[3px] h-9 bg-[#265344] rounded-l-sm"></div>
            <div class="absolute -left-[3px] top-40 w-[3px] h-12 bg-[#265344] rounded-l-sm"></div>
            <div class="absolute -right-[3px] top-32 w-[3px] h-14 bg-[#265344] rounded-r-sm"></div>

            <!-- Screen Inner Bezel -->
            <div class="relative w-full overflow-hidden rounded-[38px] bg-[#EBF7F2] aspect-[9/19.5] border border-black/10 flex flex-col">
                
                <!-- Dynamic Island / Speaker Island -->
                <div class="absolute top-2.5 left-1/2 -translate-x-1/2 z-30 w-24 h-5 bg-[#0a1813] rounded-full flex items-center justify-between px-2.5 shadow-sm">
                    <div class="w-2.5 h-2.5 rounded-full bg-[#162f26] border border-white/5"></div>
                    <div class="w-1.5 h-1.5 rounded-full bg-[#4E9F85]/40"></div>
                </div>

                <!-- Actual App Screen Content -->
                <div class="relative w-full h-full overflow-y-auto overscroll-contain">
                    <img
                        v-if="!imageError"
                        :src="imageSrc"
                        :alt="altText"
                        class="w-full h-auto object-cover object-top block transition-opacity duration-300"
                        loading="lazy"
                        @error="handleImageError"
                    />

                    <!-- Fallback Conceptual UI if image not found -->
                    <div v-else class="w-full h-full bg-[#F4FAF7] p-5 pt-12 flex flex-col text-primary font-body">
                        <div class="flex items-center justify-between pb-3 border-b border-[#0D3B2E]/10">
                            <span class="font-heading font-bold text-base text-primary">PLASVORA</span>
                            <div class="w-7 h-7 rounded-full bg-secondary/20 flex items-center justify-center text-xs text-primary font-semibold">P</div>
                        </div>
                        <div class="mt-4 p-4 rounded-2xl bg-white shadow-sm border border-secondary/15">
                            <p class="text-xs text-secondary font-medium uppercase tracking-wide">Pemanfaatan Plastik</p>
                            <h4 class="font-heading font-semibold text-sm mt-1">Eksplorasi Ide Kreasi</h4>
                            <p class="text-xs text-neutral mt-1">Panduan lengkap langkah daur ulang.</p>
                        </div>
                        <div class="mt-3 p-4 rounded-2xl bg-tertiary border border-secondary/20">
                            <p class="text-xs text-primary font-semibold">Katalog Material</p>
                            <p class="text-xs text-neutral mt-1">PET, HDPE, PP siap dimanfaatkan kembali.</p>
                        </div>
                    </div>
                </div>

                <!-- Bottom Home Indicator -->
                <div class="absolute bottom-1.5 left-1/2 -translate-x-1/2 z-30 w-28 h-1 bg-black/30 rounded-full"></div>
            </div>
        </div>

        <!-- Optional Subtle Badge under Mockup -->
        <div v-if="badgeText" class="mt-3 text-xs font-medium text-neutral/80 bg-white/70 backdrop-blur-sm px-3 py-1 rounded-full border border-secondary/20 shadow-xs">
            {{ badgeText }}
        </div>
    </div>
</template>

