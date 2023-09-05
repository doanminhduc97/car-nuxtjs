<template>
    <div class="mt-5">
        <div class="mb-10">
            {{ description }}
        </div>
    </div>
</template>
<script setup>

const props = defineProps({

    description: String,
});
</script>