<template>
    <div class="flex h-screen justify-center items-center flex-col">
        <h1 class="text-9xl">{{error.statusCode}}</h1>
        <p class="mt-7 text-4xl">message: {{error.message}}</p>
        <!-- <p class="mt-7 text-4xl">description: {{error.description}}</p>
        <p class="mt-7 text-4xl">cause: {{error.cause}}</p>
        <p class="mt-7 text-4xl">name: {{error.name}}</p>
        <p class="mt-7 text-4xl">statusMessage: {{error.statusMessage}}</p>
        <p class="mt-7 text-4xl">url: {{error.url}}</p> -->
        <button class="rounded mt-7 text-2xl bg-blue-400 px-7 py-4 text-white" @click="handleError">Go Back</button>
    </div>
</template>

<script setup>

const error = useError();

const handleError = () => {
    clearError({
        redirect: "/"
    });
};
</script>