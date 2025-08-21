<template>

    <div class="h-screen bg-amber-200">
        <h2>{{ title }}</h2>
        <p>This is a description of About Component Two.</p>
    </div>
</template>
<script>
export default {
    name: 'AboutComponentTwo',
    setup() {
        // Setup logic for AboutComponentTwo
    },
    data(){
        
        return {
            // Data properties for AboutComponentTwo
            title: 'About Components Two',
        };
    }
};
</script>