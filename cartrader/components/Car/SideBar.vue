<template>
    <div class="shadow border w-64 mr-10 z-30 h-[190px]">
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
            <h3>Location</h3>
            <h3 @click="updateModal('location')" class="text-blue-400 capitalize" id="location">{{ route.params.city }}</h3>
            <div v-if="modal.location" class="absolute border shadow left-56 p-5 top-1 -m-1 bg-white" id="popupLocation">
                <input v-model="city" type="text" class="border p-1 rounded" id="inputLocation">
                <button @click="onchangeLocation" class="bg-blue-400 w-full mt-2 rounded text-white p-1" id="btnLocation">
                    Apply
                </button>
            </div>
        </div>
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
            <h3>Make</h3>
            <h3 class="text-blue-400 capitalize">Toyota</h3>
        </div>
        <div class="p-5 flex justify-between relative cursor-pointer border-b">
            <h3>Price</h3>
            <h3 class="text-blue-400 capitalize">Any</h3>
        </div>
    </div>
</template>

<script setup>
    const modal = ref({
        make: false,
        location: false,
        price: false,
    })
    document.addEventListener('click', (e) => {
        if (e.srcElement.id === 'location' || e.srcElement.id === 'inputLocation' || e.srcElement.id === 'btnLocation' || e.srcElement.id === 'popupLocation') {
            modal.value.location = true;
        } else {
            modal.value.location = false;
        }
    })
    
    // onUnmounted(() => {
    //     document.removeEventListener("click");
    // })
    const updateModal = (key) => {
        modal.value[key] = !modal.value[key];
    }

    const city = ref('');
    const route = useRoute();

    const onchangeLocation = () => {
        if(!city.value) return;
        if (!isNaN(parseInt(city.value))) {
            throw createError({
                statusCode: 400,
                message: 'Invalid ctiy format'
            })
        }
        updateModal('location');
        navigateTo(`/city/${city.value}/car/${route.params.make}`);
        city.value = "";
    }

</script>