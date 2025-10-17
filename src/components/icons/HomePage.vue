<template>
    <HeaderComponent/>
    <AboutComponent/>
    <CardComponent/>
    <FooterComponent/>
</template>
<script setup>
import HeaderComponent from './HeaderComponent.vue';
import AboutComponent from './AboutComponent.vue';
import FooterComponent from './FooterComponent.vue';
import CardComponent from './CardComponent.vue';
import { onMounted } from 'vue';

onMounted(() => {
    document.title = 'My Profile';
})
</script>