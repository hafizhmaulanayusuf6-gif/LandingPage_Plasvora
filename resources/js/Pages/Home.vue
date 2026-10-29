<script setup>
import Navbar from '../Components/Navbar.vue';
import HeroSection from '../Components/HeroSection.vue';
import FeatureSummary from '../Components/FeatureSummary.vue';
import MainFeatures from '../Components/MainFeatures.vue';
import VisualBanner from '../Components/VisualBanner.vue';
import ExplorationCards from '../Components/ExplorationCards.vue';
import PotentialBenefits from '../Components/PotentialBenefits.vue';
import AppPreviewSection from '../Components/AppPreviewSection.vue';
import FinalCta from '../Components/FinalCta.vue';
import FooterSection from '../Components/FooterSection.vue';
</script>

<template>
    <div class="min-h-screen bg-[#F8FAF9] text-[#0D3B2E] font-body flex flex-col selection:bg-[#4E9F85] selection:text-white">
        <!-- 1. Top Navbar -->
        <Navbar />

        <main class="flex-grow">
            <!-- 2. Hero Section with Smartphone Mockup -->
            <HeroSection />

            <!-- 3. Floating Feature Summary -->
            <FeatureSummary />

            <!-- 4. Main Feature Highlights (3 Left, Phone Center, 3 Right) -->
            <MainFeatures />

            <!-- 5. Full-Width Visual Banner -->
            <VisualBanner />

            <!-- 6. Exploration Cards (Inspirasi, Panduan, Material) -->
            <ExplorationCards />

            <!-- 7. Potential Benefits (Untuk Kreator & Pelaku Material) -->
            <PotentialBenefits />

            <!-- 8. Interactive App Preview Showcase -->
            <AppPreviewSection />

            <!-- 9. Final Call To Action -->
            <FinalCta />
        </main>

        <!-- 10. Footer Section -->
        <FooterSection />
    </div>
</template>
