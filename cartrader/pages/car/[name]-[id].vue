<template>
    <div v-if="car">
        <!-- <CarNavBar /> -->
        <!-- car detail page -->
        <!-- <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5"> -->
            <CarDetailHero :car="car"/>
            <CarDetailAttributes :features="car.features"/>
            <CarDetailDescription :description="car.description"/>
            <CarDetailContact />
        <!-- </div> -->
        <!-- car detail page -->
    </div>
</template>
<script setup>
const route = useRoute();
const {toTitleCase} = useUtilities();
const {cars} = useCars();

const car = computed(() => {
    return cars.find((c) => {
        return c.id === parseInt(route.params.id);
    });
});

if (!car.value) {
    throw createError({
        statusCode: 404,
        message: `Car with id of ${route.params.id} does not exist`
    })
}

useHead({
    title: toTitleCase(route.params.name)
})


definePageMeta({
  layout: "custom"
});

</script>